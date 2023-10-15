Adds one or more members to a sorted set: `ZADD products 45 monitor`
Return the score of a member in a sorted set: `ZSCORE products monitor`
Remove a member from a sorted set: `ZREM products monitor`
Get numbers of sorted set: `ZCARD products`
Return the cound of members in a sorted set that have scores within a range:
- `ZCOUNT products 0 5`
- `ZCOUNT products 0 (50`
- `ZCOUNT products (0 50`
- `ZCOUNT products (0 +inf`
- `ZCOUNT products -inf 40`
Return a range of members and WITHSCORES(optional) 
- `ZRANGE product 1 2 WITHSCORES`
- `ZRANGE product 1 2`
- `ZRANGE product 1 2 REV` Reverse before get
- `ZRANGE product 1 2 REV limit 1 2` // reverse then skip 1, give back 2 next records
- `ZRANGE product 1 2 REV limit 0 2` // reverse then skip 0, give back 2 first records
Delete last members: `ZPOPMAX products 2`
Delete first members: `ZPOPMAX products 1`
Adjust a member's score by the given amount `ZINCRBY products 13 monitor`