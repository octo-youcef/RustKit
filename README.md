# RustKit
A set of CLI tools built in Rust to simplify operation and navigation

## Getting Started
RustKit ships with a MakeFile for easy installation of components
```bash
make install
```

Alternatively individual components can be installed using `cargo instal --path <component_dir>` e.g.
```bash
cargo install --path finder/
```

## Finder
A tool to replace the complex bash `find` logic which searches for files (optionally) containing some string or regular expression pattern.

### The challenge
Finding files containing some string is a common use case in the shell, however the command is cumbersome:
```bash
# Bash command
find <dir> \
    -type f \
    -name <file pattern> \
    -exec grep -iH <search pattern> {} \;
```

Instead, `finder` provides a lightweight wrapper for this common command.

### Usage
```bash
Usage: finder [OPTIONS] [PATH]

Arguments:
  [PATH]  Optional path to operate on, defaults to CWD

Options:
  -f, --file-pattern <FILE_PATTERN>      File pattern to filter results
  -s, --search-pattern <SEARCH_PATTERN>  Search pattern find in result files
  -i, --case-insensitive                 Flag for case insensitive search
  -h, --help                             Print help
  -V, --version                          Print version
```
