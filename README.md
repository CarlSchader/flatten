Sure, here's a README.md file for your project:

# Flatten

Flatten is a Rust command-line tool that copies files from multiple input directories into a single output directory, resolving any naming conflicts by adding a suffix to the file name before the extension.

## Usage

```
flatten <dir1> <dir2> ... <out-dir>
```

- `<dir1>` `<dir2>` ... are the input directories containing the files you want to copy.
- `<out-dir>` is the output directory where the files will be copied to.

If a file with the same name already exists in the output directory, a suffix (e.g., `-1`, `-2`, ...) will be added to the new file's name before the extension to avoid overwriting.

## Example

```
flatten /path/to/dir1 /path/to/dir2 /path/to/output
```

This command will copy all files from `/path/to/dir1` and `/path/to/dir2` into the `/path/to/output` directory, resolving any naming conflicts by adding a suffix.

## Implementation Details

The program follows these steps:

1. Parse the command-line arguments to get the input directories and output directory.
2. Create the output directory if it doesn't exist.
3. Traverse each input directory recursively.
4. For each file encountered:
   - Check if a file with the same name already exists in the output directory.
   - If not, copy the file to the output directory with its original name.
   - If a file with the same name exists, add a suffix (e.g., `-1`, `-2`, ...) to the new file's name before the extension and copy it to the output directory.
5. Repeat step 4 for all files in all input directories.

## Dependencies

This program uses the standard Rust libraries:

- `std::env`
- `std::fs`
- `std::collections::HashMap`
- `std::ffi::OsString`
- `std::path::Path`

No external dependencies are required.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
