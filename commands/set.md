Use cases:
1. Check unique: if user exists in set of users to create new one or not
2. Check relationship between different records
- Which items do user with id 1 like?
   `SMEMBERS users#1:likes`
- How many items does user with id 1 like?
` SCARD users#1:likes`
- Does user with id 1 like the with with id 0?
` SISMEMBER users#1:likes 0`
3. Find common attributes between different records
- Which items do both user 45 and user 32 like?
4. General list of elements where order doesnt matter

https://redis.io/commands/?group=set

Add items to set
```
SADD a 1 2 3
SADD b 1 2 3 4 5 6
SADD c 1 2 3 4 5 6 7 0
```

Show items 
```
SMEMBERS  a
SMEMBERS  b
SMEMBERS  c
```

Check 1 item: 
`SISMEMBER  c 1`

Check multiple item: 
`SMISMEMBER a 1 0`


- Union => return all unique from elements
```
SUNION a b c
```
- Intersect => return elements that exist in all sets
```
SINTER a b c
```
- Diff => return elements that exist only in one set
```
SDIFF c b a
```

With suffix STORE act like count total filter 
```
SUNIONSTORE count a b c
SINTERSTORE count a b c
SDIFFSTORE count c b a
```

Count items in set
```
SCARD a
```

Remove item in set
```
SREM a 1
```

Get number of items from index
SSCAN a 0 count 2