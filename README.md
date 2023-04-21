# Single binary benchmark score with Node.js

## How to build

```sh
# Put excutable binary from C
gcc -o hello_world hello_world.c

# Put excutable binary from Node.js
## Create blob
node --experimental-sea-config sea-config.json
## Create Node.js copy
## ref: https://ss64.com/bash/command.html
cp $(command -v node) hello-world
## Injection binary blob to Node.js
## ref: https://github.com/nodejs/postject
npx postject hello-world NODE_SEA_BLOB sea-prep.blob \
    --sentinel-fuse NODE_SEA_FUSE_fce680ab2cc467b6e072b8b5df1996b2
```

## Benchmark

-   gcc version 11.3.0 (Ubuntu 11.3.0-1ubuntu1~22.04)
-   node v20.0.0
-   CPU: AMD Athlon 200GE

| Language | Filesize(Byte) | `time` result                                |
| -------- | -------------- | -------------------------------------------- |
| C        | 15,968         | 0.00s user 0.00s system 77% cpu 0.002 total  |
| Node.js  | 95,685,760     | 0.04s user 0.01s system 101% cpu 0.053 total |
