# Hash Tables

Hash Tables are data structures that contain key value pairs and are stored in dictonaries.

The placement of the values are found by large keys and we hash them to smaller keys. 

There are two steps to hashing:
1. The element is converted to an integer by using a hash function. The element can be used as an index to store the original element.
2. The element is stored inside of the hash table where it can be retrieved using a hash key.

```
hash = hashfunc(key)
index = hash % array_size
```

In this method, the hash is independent of the array size and it is then reduced to an index (a number between 0 and array_size − 1) by using the modulo operator (%).

When creating a hashing function, it's important to have a good hashing mechanism and should follow these three guidelines: 

1. Hash functions should be easy to compute
2. Hash functions should provide a uniform distribution and should not result in clustering. 
3. Hash function should avoid collisions

If a collision occurs, we resolve by creating a linked list. There are other methods to resolve collisions and they are linear probing, quadratic probing, and double hashing.

## Internal Methods

- `Add()` - Sends the key to the `GetHash` method and goes to that index. if there's something there, add the key value pair to the data structure.
- `Find()` - Takes in a key, gets the hash, and goes to that index. Then it will iterate through the bucket and see if the value exists.
- `Contains()` - Grabs a key and returns a boolean if the value exists inside of the hash table.
- `GetHash()` - Accepts a key, conduct the hash, and return the index of the array where the key/value should be placed. 