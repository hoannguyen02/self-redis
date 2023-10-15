https://redis.io/commands/?group=string

- SET
    - key => key to set
    - value => value to store
    - EX | PX | EXAT | PXAT | KEEPTTL => option when value expire
    - NX | XX => only set this key if not exist yet
    - GET => return the previous value store at this key
```
SET color red
SET color green GET
get color
SET color red EX 2
```
- SETEX is similar to SET with EX option => only run if record not exist
```
SETEX color 2 red
```
- SETNX is similar to SET with NX option => only run if record not exist
```
```
- MSET is set multiple values
```
MSET color red model ford
GET color
GET model
```

- DEL 
```
GET color
DEL color
GET color
```
- GETRANGE 
```
GETRANGE color 0 2
```

- SETRANGE 
```
SETRANGE model 2 blue
GET model
```