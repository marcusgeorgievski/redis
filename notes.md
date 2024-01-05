# Redis

-   Databse
-   Data persistance
-   JSON support
-   Search
-   Redis OM

## Data Types

**key:value pairs**

-   string
-   sets
-   hashes (collection of kv pairs)
-   lists
-   Sorted sets
-   more...

WWKzSHHMzANjQ3viA0HkmHvgbtt6FhJh
redis://default:WWKzSHHMzANjQ3viA0HkmHvgbtt6FhJh@redis-12406.c309.us-east-2-1.ec2.cloud.redislabs.com:12406

## Commands

```sql
SET k v
MSET k v [k v ...] -- set multiple k:v pairs
SETNAME k start value -- does not append, it replaces

GET k
MGET k [k ...]
GETRANGE k start stop -- can index like python using negative ints

INCR k -- inc val by 1
INCRBY k n -- inc val by n

DECR k
DECRBY k
```

## Options

```sql
SET k v EX n -- k:v pair expires after n seconds
SET k v NX n -- set if kv DNE
SET k v XX n -- set if kv exists
SET k v GET -- get prev value if exists, else nil
```

## Sets

`m` = member of set

```sql
SADD k m [m ...]
SREM k m [m ...]
SUNION k [k ...]
SISMEMBER k m
SDIFF k1 [k2 ...] -- returns members in k1 not in k2
```

## Lists

`e` = element of list

-   linked lists

```sql
LPUSH k e [e ...]
RPUSH k e [e ...]

LPOP k
RPOP k
LLEN k

-- k -2 -1 valid, k -1 -2 not
LRANGE k start stop
RRANGE k start stop

LINDEX k i
LPOS k e
```

## Hashes

`f` = field
`v` = value

-   collection of kv pairs, like a js object
-   values must be strings
-   name convention -> `object:id`

```sql
HSET k f v [f v ...]

HGET k f
HGETALL k -- gets k and f
HKEYS k
HVALS k

HEXISTS k f
HLEN k -- num of fields

HDEL k f [f ...]
DEL k
```

## Sorted Set

```sql
ZADD key score member [score member ...]
```
