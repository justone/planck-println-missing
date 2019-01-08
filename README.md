Potential bug in Planck.

How to reproduce:

1. Run `./script`
2. Edit `src/library.clj` and change the message in the `test-print` function.
3. Run `./script` again.

The second time `script` is run, an error is printed:

```
WARNING: Use of undeclared Var library/println at line 4 /.../e62af8d2353af175380ccc6f60072915/src/library.cljc
Test print in main
undefined is not an object (evaluating 'library.println.call')
```

It appears that the `println` function is not found.  If the `.planck_cache/` directory is removed, the next run of `script` is fine.
