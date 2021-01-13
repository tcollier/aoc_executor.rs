# AoC Rust Executor

Rust executor for the [Advent of Code Solver](https://github.com/tcollier/aoc_solver).

## Template Code

**IMPORTANT**: The executor code needs to be soft linked from the challenge day directory in order for rustc to compile correctly, e.g.

```
% cd 2020/01
% ln -s /path/to/src/util.rs
```

```rs
// main.rs
use std::env;

mod util;

struct Day1Solution {
  input: Vec<String>
}

impl util::Solution for Day1Solution {
  fn part1_result(&self) -> String {
    // compute and return part 1 solution
  }

  fn part2_result(&self) -> String {
    // compute and return part 2 solution
  }
}

fn main() {
  let input = // load input
  let solution = Day1Solution { input: input };
  let executor = util::Executor::new(&solution as &util::Solution);
  let args = env::args().collect();
  executor.run(args);
}
```
