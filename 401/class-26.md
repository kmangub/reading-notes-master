# Django Best Practices
Link: https://djangostars.com/blog/configuring-django-settings-best-practices/

Bottome Line Up Front:

- Keep settings in environment variables.
- Write default values for production configuration (excluding secret keys and tokens).
- Don’t hardcode sensitive settings, and don’t put them in VCS.
- Split settings into groups: Django, third-party, project.
- Follow naming conventions for custom (project) settings.

### Settings File
Managing the settings file is very important when it comes to deploying our website. We manage it because we want to control what is being shown and what isn't whilst making the website run with no issues. Some of these issues are: 

- Having different environments
- Sensitive data
- Sharing settings between team members 
- Django settings is a Python code

A best practice would be to separate the settings file in each environment so we can easily share our settings with other developers. The only issue is handling secret passwords and tokens. This is where environ comes in.

### 12 Factors 

- Codebase
- Dependencies
- Config
- Backing services
- Build, release, run
- Processes
- Port binding
- Concurrency
- Disposability
- Dev/prod parity
- Logs
- Admin processes

# SSH
Link: https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work

Secure Shell (SSH) is an admin protocol that allows users to control and modify their remote servers over the Internet. It gives a way to authenticate a user, send inputs to the host, and return an output to the client. SSH has three parts:

```
ssh {user}@{host}
```

Where `ssh` is the command we run to open a SSH connection, `user` is the account we want to access, and `host` is the computer we want to access. Next we will be prompted to put in a password for the account. If it is successful, a new terminal window will open up.

## Encryption Techniques

The three encryption technologies used are:

- Symmetrical encryption - Same key to encrypt and decrypt
- Asymmetrical encryption - different keys to encrypt and decrypt
- Hashing 

## Basic Algorithm

1. Both the client and the server agree on a very large prime number, which of course does not have any factor in common. This prime number value is also known as the seed value.
2. Next, the two parties agree on a common encryption mechanism to generate another set of values by manipulating the seed values in a specific algorithmic manner. These mechanisms, also known as encryption generators, perform large operations on the seed. An example of such a generator is AES (Advanced Encryption Standard).
3. Both the parties independently generate another prime number. This is used as a secret private key for the interaction.
4. This newly generated private key, with the shared number and encryption algorithm (e.g. AES), is used to compute a public key which is distributed to the other computer.
5. The parties then use their personal private key, the other machine’s shared public key and the original prime number to create a final shared key. This key is independently computed by both computers but will create the same encryption key on both sides.
6. Now that both sides have a shared key, they can symmetrically encrypt the entire SSH session. The same key can be used to encrypt and decrypt messages (read: section on symmetrical encryption).


