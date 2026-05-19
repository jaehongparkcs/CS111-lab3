# Hash Hash Hash
TODO introduction
Making a hash map that is safe to use concurrently in an operating system using `pthread_mutex` locks

## Building
```shell
TODO
make
```

## Running
```shell
TODO how to run and results
./hash-table-tester -t 8 -s 50000
```
Results:
Generation: 146,634 usec
Hash table base: 1,827,811 usec
- 0 missing
Hash table v1: 10,134,325 usec
- 0 missing
Hash table v2: 9,689,007 usec
- 0 missing

## First Implementation
In the `hash_table_v1_add_entry` function, I added TODO

### Performance
```shell
TODO how to run and results
```
Version 1 is a little slower/faster than the base version. As TODO

## Second Implementation
In the `hash_table_v2_add_entry` function, I TODO

### Performance
```shell
TODO how to run and results
```

TODO more results, speedup measurement, and analysis on v2

## Cleaning up
```shell
TODO how to clean
```