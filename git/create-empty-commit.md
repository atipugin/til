# Create empty commit

We can create "empty" (without any actual changes) commits using `--allow-empty`
flag:

```shell
git commit --allow-empty -m "Trigger CI"
```

It might be useful if you need to trigger CI workflows etc.
