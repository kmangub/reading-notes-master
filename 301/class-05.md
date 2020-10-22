# Heroku Deployment

Heroku is a cloud application development platform and it's really simple for businesses and companies to build an app that caters to the customers and runs in the cloud.

The installation process is very simple. I followed these steps:

1. I logged on to Heroku.

2. On my terminal, I used the command `heroku` followed by a `heroku login` command. This will oepn up my browser. 

3. I was already logged in on my browser, so all I have to do at this point was to click the log in button.

4. I then checked to see if I had the latest versions of **node**, **npm**, and **git**.

5. I cloned a sample app , which comes with a `package.json` file.

6. I created the app with the command `heroku create` and it will give me a random generated name for my app.

7. I used the command `git push heroku main` and now it's deployed. 

8. I made sure that app was working by using the `heroku ps:scale web=1` command.

9. A shortcut to go from the terminal to the browser is  `heroku open`.

10. To view logs, I used the `heroku logs --tail` command.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)
