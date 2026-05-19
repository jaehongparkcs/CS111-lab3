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
./hash-table-tester -t 4 -s 50000
```
*Used -t 4 since computer has maximum 4 cores to operate
Results:
Generation: 71,618 usec
Hash table base: 455,627 usec
- 0 missing
Hash table v1: 1,748,388 usec
- 0 missing
Hash table v2: 166,023 usec
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