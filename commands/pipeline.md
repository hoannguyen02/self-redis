
Example with golang (with nodejs we have to use Promise.all([....]))
```
 client := redis.NewClient(&redis.Options{
        Addr:     "localhost:6379",
        Password: "",
        DB:       0,
    })

    pipe := client.Pipeline()
    for i := 0; i < 10; i++ {
        pipe.Set("testkey:" + strconv.Itoa(i), strconv.Itoa(i), 0)
    }

    _, err = pipe.Exec()
    if err != nil {
        panic(err)
    }
    for k, v := range cmds {
        val, err := v.Result()
        if err != nil {
            panic(err)
        }
        fmt.Printf("    %s  %s\n", k, val)
    }
```