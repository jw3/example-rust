example rust
===



### shared library to cpp
- `rustc --crate-type=cdylib src/shared.rs`

```
#! readelf -d libshared.so 

Dynamic section at offset 0x133168 contains 28 entries:
  Tag        Type                         Name/Value
 0x0000000000000001 (NEEDED)             Shared library: [libdl.so.2]
 0x0000000000000001 (NEEDED)             Shared library: [librt.so.1]
 0x0000000000000001 (NEEDED)             Shared library: [libpthread.so.0]
 0x0000000000000001 (NEEDED)             Shared library: [libgcc_s.so.1]
 0x0000000000000001 (NEEDED)             Shared library: [libc.so.6]
 0x0000000000000001 (NEEDED)             Shared library: [ld-linux-x86-64.so.2]
```

```
#! readelf -Ws libshared.so | grep doit
    69: 0000000000002f90    68 FUNC    GLOBAL DEFAULT   11 doit
   904: 0000000000002f90    68 FUNC    GLOBAL DEFAULT   11 doit
```
