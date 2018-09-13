# rust-mnemonic-benchmark
Benchmark different implementations for a mnemonic implementation

## Important Note
This is **not** a full mnemonic implementation as the checksum is missing!
The sole purpose of this repository is benchmarking.

## Instructions
This benchmark currently only runs with the nightly compiler (as it makes use of `#![feature(test)]`).
You can explore it via:
* `rustup run nightly cargo run`
* `rustup run nightly cargo test`
* and most importantly `rustup run nightly cargo bench`.

## Results

The implementation using BitVecs and my own iterator seems to be the fastest of these options:
```
test tests::bench_str           ... bench:       4,456 ns/iter (+/- 510)
test tests::bench_vec           ... bench:       1,261 ns/iter (+/- 79)
test tests::bench_vec_itertools ... bench:       2,730 ns/iter (+/- 606)
```
