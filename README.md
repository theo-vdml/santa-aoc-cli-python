# 🎅 Advent of Code Python CLI

A lightweight CLI boilerplate for solving [Advent of Code](https://adventofcode.com) puzzles in Python.

> **⚠️ Beta Notice:** This is a beta project and is likely to change and be improved over time. Expect breaking changes as features are added and refined.

## Features

-   **Simple CLI** - Run solutions with `./santa [day]`
-   **Auto-initialization** - Scaffold new days with `--init`
-   **Test mode** - Separate test inputs for debugging
-   **Benchmarking** - Average runtime over multiple runs
-   **Range execution** - Run multiple days at once
-   **Clean output** - Colored, formatted results

## Quick Start

1. **Setup environment:**

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

2. **Initialize a new day:**

```bash
./santa --init 1
```

This creates:

-   `day/01.py` - Solution template
-   `inputs/01.txt` - Your puzzle input
-   `inputs/01_test.txt` - Test input

3. **Write your solution in `day/01.py`:**

```python
class Solution:
    def __init__(self, input_data: str):
        self.data = input_data.strip()
        # Parse your input

    def part_one(self) -> int | str:
        # Solve part 1
        pass

    def part_two(self) -> int | str:
        # Solve part 2
        pass
```

4. **Run it:**

```bash
./santa 1           # Run with real input
./santa 1 --test    # Run with test input
```

## Usage

```bash
./santa                      # Run the most recent day
./santa 1                    # Run day 1 with inputs/01.txt
./santa 1 --test             # Run day 1 with inputs/01_test.txt
./santa 1 --file custom.txt  # Run day 1 with custom input file
./santa 1 --one              # Run ONLY part one
./santa 1 --two              # Run ONLY part two
./santa 1 --average 100      # Run 100 times, show average performance
./santa 5-10                 # Run days 5 through 10
./santa --all                # Run ALL completed days
./santa --init 3             # Initialize day 3 files
./santa --clean 3            # Delete day 3 files (careful!)
./santa --help               # Show help message
```

## Project Structure

```
.
├── santa              # Main CLI runner
├── day/               # Solution files (01.py, 02.py, ...)
├── inputs/            # Input data
│   ├── 01.txt         # Real input
│   └── 01_test.txt    # Test input
├── day_template.py    # Template for new solutions
└── requirements.txt   # Dependencies
```

## Git Setup

**Important:** By default, the `day/` and `inputs/` folders are in `.gitignore` to keep this boilerplate clean.

If you want to save your solutions to git, you need to:

1. Edit `.gitignore` and remove these lines:

    ```
    inputs
    day
    ```

2. Then commit your solutions:
    ```bash
    git add day/ inputs/
    git commit -m "Add my AoC solutions"
    ```

**Note:** Advent of Code asks that you don't publicly share puzzle inputs. Consider keeping `inputs/` in `.gitignore` and only tracking your solution code in `day/` if you want to share your solutions publicly.

## Tips

-   The `__init__` method runs fresh for both part_one() and part_two()
-   Store parsed data in `self.whatever` for use in both parts
-   Use `--test` while developing, switch to real input when ready
-   Benchmark slow solutions with `--average 10`

## License

Use this however you want. Happy solving! 🎄
