# Rust Learning Project

A 16-week study project for learning Rust by implementing the algorithms from *Algorithms Illuminated, Part 1* while reading *The Rust Programming Language* (2023 edition).

## Goals

- Work through all 20 chapters of the Rust book.
- Implement the algorithms from the 12 chapters of Algorithms Illuminated, Part 1 in Rust, with tests.
- Build one reusable library of algorithms and data structures that grows week by week.

## Project layout

```
rust-learning/
├── Cargo.toml              # workspace file listing the members below
├── README.md
├── book/                   # Rust book exercises, one small project each
│   ├── hello_world/        # Week 1
│   ├── guessing_game/      # Week 1 (Ch 2)
│   ├── minigrep/           # Week 9 (Ch 12)
│   └── web_server/         # Week 16 (Ch 20)
├── algos/                  # one library crate, grows every week
│   ├── Cargo.toml
│   ├── src/
│   │   ├── lib.rs          # declares the modules
│   │   ├── multiplication.rs   # AI Ch 1: grade-school, Karatsuba
│   │   ├── sorting/        # merge sort, quicksort
│   │   ├── selection.rs    # AI Ch 6
│   │   ├── graph/          # adjacency list, BFS/DFS, SCC, Dijkstra
│   │   ├── heap.rs
│   │   ├── bst.rs
│   │   └── hashing.rs
│   ├── tests/              # integration tests, compared against std
│   ├── benches/            # timing comparisons
│   └── examples/           # small runnable programs
├── data/                   # test files from algorithmsilluminated.org
└── notes/                  # short notes per week
```

The book exercises are standalone programs. The algorithms all live in the `algos` crate so later weeks can reuse earlier work (for example, Dijkstra on top of your own heap).

## Getting started

1. Install Rust with [rustup](https://rustup.rs) and check it with `rustc --version`.
2. Clone this repository and open its folder.
3. Run the whole workspace's tests:

   ```
   cargo test
   ```

4. Run a book exercise:

   ```
   cargo run -p hello_world
   ```

5. Lint before committing:

   ```
   cargo clippy
   ```

## Data files

Large input files from the book's companion site (algorithmsilluminated.org) are not stored in git. Download them into `data/` and keep them listed in `.gitignore`.

## Weekly workflow

1. Read the Rust chapters (2-3 hours).
2. Read the matching algorithms chapter (2 hours).
3. Implement the algorithm in Rust, with tests (2-3 hours).
4. Run `cargo test` and `cargo clippy`.
5. Write a few lines in `notes/` about what confused you and what you learned.
6. Commit with a message like `Week 3: merge sort, ownership notes`.

When a new Rust chapter gives you a better tool (traits, iterators, error handling), go back and refactor an earlier module, and note the change.

## Progress

### Phase 1: Rust basics with simple algorithms

- [ ] Week 1: Rust Ch 1-2, AI Ch 1. Hello World, guessing game, grade-school multiplication
- [ ] Week 2: Rust Ch 3, AI Ch 2. Asymptotic notation, timing O(n) vs. O(n²)
- [ ] Week 3: Rust Ch 4, AI Ch 1. Ownership, merge sort
- [ ] Week 4: Rust Ch 5-6, AI Ch 3. Counting inversions, Karatsuba with `BigNum`

### Phase 2: Collections, errors, generics

- [ ] Week 5: Rust Ch 7-8, AI Ch 4. Modules, library crate, benchmark harness
- [ ] Week 6: Rust Ch 9, AI Ch 5. QuickSort, error handling
- [ ] Week 7: Rust Ch 10, AI Ch 5-6. Generic sorts, linear-time selection
- [ ] Week 8: Rust Ch 11, AI Ch 1-6 review. Tests for everything so far

### Phase 3: Graphs

- [ ] Week 9: Rust Ch 12, AI Ch 7. Adjacency lists, Karger's min cut, minigrep
- [ ] Week 10: Rust Ch 13, AI Ch 8. BFS, DFS, topological sort
- [ ] Week 11: Rust Ch 8 and 14, AI Ch 8. Strongly connected components
- [ ] Week 12: Rust Ch 15, AI Ch 9. Dijkstra, array version then `BinaryHeap`

### Phase 4: Data structures and capstone

- [ ] Week 13: Rust Ch 16, AI Ch 10. Min-heap, heap-based Dijkstra, median maintenance
- [ ] Week 14: Rust Ch 17-18, AI Ch 11. Binary search tree
- [ ] Week 15: Rust Ch 19, AI Ch 12. Hash table, Bloom filter
- [ ] Week 16: Rust Ch 20, capstone. Web server, benchmark suite or CLI tool

## Resources

- [The Rust Programming Language](https://doc.rust-lang.org/book/)
- [Rust by Example](https://doc.rust-lang.org/rust-by-example/)
- [Rustlings](https://github.com/rust-lang/rustlings)
- [Algorithms Illuminated companion site](https://www.algorithmsilluminated.org)
