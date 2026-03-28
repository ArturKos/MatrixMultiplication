# MnozenieMacierzy

High-performance 1000x1000 matrix multiplication comparing sequential, parallel, and polyhedral-optimized approaches.

## Variants

| Variant | Description |
|---------|-------------|
| `mmul.c` | Sequential baseline |
| `mmul.pluto.c` | OpenMP parallel with Pluto polyhedral tiling optimization |
| `mmul.pluto.orgin.c` | Original Pluto-optimized version |

## Features

- OpenMP multithreading with configurable thread count
- Cache tiling via Pluto polyhedral compiler for improved data locality
- Benchmark timing with `omp_get_wtime()` for multiplication and total execution
- Results logged to timestamped files

## Build & Run

```bash
gcc -lgomp -fopenmp -O3 mmul.pluto.orgin.c -lm -o mmul.p
./mmul.p <thread_count>
```
