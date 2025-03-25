## Getting Started

- Executable binaries are available for download on the [GitHub Releases page][releases].
- Download the binary for your platform (Windows, macOS, or Linux) and extract the archive.
- The archive contains an `mdbook` executable which you can run to build your books.

> To make it easier to run, put the path to the binary into your `PATH`.

[releases]: https://github.com/rust-lang/mdBook/releases

## Installation Steps
```sh
$ git clone https://github.com/Blender4Pepu/blender_book
$ cd blender_book
$ mdbook serve --open
```
## Build the Book
After cloning the repository, you can also build the book manually by running the following command:

```sh
$ cd blender_book
$ mdbook build
```

This will generate the output in the `book/` directory. You can then serve the book or deploy it as needed.

## Customize the Book
To customize your book, you can edit the `book.toml` configuration file and modify its structure or appearance.

## Contributing
If you'd like to contribute to this book, feel free to open an issue or submit a pull request. 
