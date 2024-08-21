Checks each element within vector `a` of size `dims` against a provided broadcast value
comparing if they are **_greater than_** returning a mask vector of the same type.

### Pseudocode

```ignore
mask = [0; dims]

for i in range(dims):
    mask[i] = a[i] > value ? 1 : 0

return mask
```

### Note on `NaN` handling on `f32/f64` types

For `f32` and `f64` types, `NaN` values are handled as always being `false` in **ANY** comparison. 
Even when compared against each other.

- `1.0 > 0.0 -> true`
- `1.0 > NaN -> false`
- `NaN > 1.0 -> false`
- `NaN > NaN -> false`

# Safety

This routine assumes: