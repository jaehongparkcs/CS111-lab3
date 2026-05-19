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
In the `hash_table_v1_add_entry` function, I added a single pthread_mutex_t directly to the main hash_table_v1 struct and used it to lock at the start of function and unlock at the end before any return calls.

### Performance
```shell
TODO how to run and results
./hash-table-tester -t 4 -s 50000
```
Result for v1: 
Hash table base: 455,627 usec
- 0 missing
Hash table v1: 1,748,388 usec
- 0 missing

Version 1 is a little slower than the base version. As there is one single global lock forcing everything to run in series creating massive overhead from having to wait for the working thread to finish along with the added work of initializing, locking, unlocking, and destorying mutex.

## Second Implementation
In the `hash_table_v2_add_entry` function, I added a pthread_mutex_t into each individual hash_table_entry structure allowing threads to access different lists to execute concurrently without blocking one another and used it to to lock at the start of function and unlock at the end before any return calls.

### Performance
```shell
TODO how to run and results
./hash-table-tester -t 4 -s 50000
```
Result for v2:
Hash table base: 455,627 usec
Hash table v2: 166,023 usec

TODO more results, speedup measurement, and analysis on v2
Was extremely faster as compared to base it was about 2.74 times faster and compared to v1 it was about 10.53 times faster.

## Cleaning up
```shell
TODO how to clean
make clean
```