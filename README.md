# SESSION2
# CTF Cybersecurity Workshop: Steganography &amp; Forensics
# CTF Cybersecurity Workshop: Steganography & Forensics

## Description

This repository is a technical guide aimed at enhancing practical skills in **Steganography** and **Forensics**, particularly within the context of **Capture the Flag (CTF)** competitions. The focus is on mastering the use of command-line tools and applying them to solve real-world challenges.

### Steganography

Steganography involves concealing information within media files such as images, typically using techniques like **Least Significant Bit (LSB)** manipulation. This technique embeds hidden data by altering the least significant bits of the image’s pixels, which does not noticeably affect the image quality.

#### Topics Covered:
- **LSB Steganography**: Learn how to manipulate the least significant bits of image files to embed and extract hidden data.
- **Steganography Tools**:
  - `steghide`: A tool for embedding and extracting data from images and audio files.
  - `zsteg`: Used to analyze PNG files for hidden data.

#### Key Commands:
- **Embed data into an image (Steghide)**:
  ```bash
  steghide embed -cf [image_file] -ef [data_file] -p [password]

