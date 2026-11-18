# Steganography Using C

## Project Overview

Steganography is a technique used to hide secret information inside an image without visibly changing its appearance.

This project implements image steganography using the C programming language. It uses the Least Significant Bit (LSB) technique to encode secret text data into a BMP image and decode the hidden information whenever required.

## Project Features

- Encode secret text files into BMP images.
- Decode hidden information from encoded BMP images.
- Uses Least Significant Bit (LSB) manipulation.
- Supports BMP input images.
- Stores the secret file extension and file size inside the image.
- Validates the magic string before decoding.
- Supports custom output image filenames.
- Uses modular programming with separate encoding and decoding files.

## Technologies Used

- Programming Language: C
- Compiler: GCC
- Image Format: BMP
- Concepts: Pointers, Structures, File Handling, Bitwise Operators, String Handling, Command-Line Arguments.

## Project Structure

```text
Steganography-using-C/
│
├── encode.c
├── encode.h
├── decode.c
├── decode.h
├── common.h
├── types.h
├── test_encode.c
├── beautiful.bmp
├── README.md
└── .gitignore
```

## Compilation

Compile the source files using GCC:

```bash
gcc test_encode.c encode.c decode.c -o steganography
```

## Encoding

To hide secret text inside an image:

```bash
./steganography -e beautiful.bmp sample_secret.txt stego.bmp
```

Here:
- `-e` specifies encoding.
- `beautiful.bmp` is the source image.
- `sample_secret.txt` is the secret text file.
- `stego.bmp` is the output image containing hidden data.

The output filename is optional. If omitted, the program creates `stego.bmp`.

## Decoding

To retrieve hidden information:

```bash
./steganography -d stego.bmp
```

To specify a decoded output filename:

```bash
./steganography -d stego.bmp decoded
```

The program retrieves the hidden file extension and creates the decoded output file.

## Working Principle

1. Read the source BMP image.
2. Check whether the image has sufficient capacity.
3. Copy the BMP header into the output image.
4. Encode a predefined magic string.
5. Encode the secret file extension and its size.
6. Encode the secret file size.
7. Hide the secret file data using LSB manipulation.
8. Copy the remaining image data.
9. During decoding, extract the hidden information from the image's least significant bits.

## Learning Outcomes

- Understanding image steganography concepts.
- Practical implementation of bitwise operations.
- Working with file pointers and binary files.
- Understanding LSB encoding and decoding.
- Handling command-line arguments.
- Implementing modular programming in C.
- Using structures and header files.

## Author

Manupriya J

## Project Domain

C Programming | Image Steganography | File Handling | Bitwise Operations
