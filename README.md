# SESSION2
# CTF Cybersecurity Workshop: Steganography &amp; Forensics
# Intro to Steganography

## Description

**Steganography** is a technique used to conceal secret information within an ordinary file or message, in such a way that it avoids detection. The hidden data can be in the form of text, image, video, or audio, and is often encrypted before being embedded into the cover medium to enhance security. Steganography can be used for both constructive purposes (like secure communications) and destructive purposes, including cyber-attacks known as **Stegware**.

---

## LSB Steganography

**LSB (Least Significant Bit) Steganography** is a method of hiding information within digital images, audio, or other media by altering the least significant bits of each pixel or sample.

- **Pixels in Images**: In an image, each pixel is made up of RGB (red, green, blue) values. Each of these values ranges from 0 to 255, which can be represented in 8 bits. By changing the least significant bits, you can embed secret information without visibly altering the image.
  ![LSB](https://miro.medium.com/v2/resize:fit:640/format:webp/0*yt4TJAYknJNKlS5W)
- **Audio Samples in .wav Files**: In audio steganography, the LSB of audio samples can be changed to hide data, similar to how pixel values are altered in images.

### Tools for LSB Steganography

 **Steghide**  
   A command-line tool used for embedding and extracting hidden data from image and audio files (e.g., bmp, jpeg, wav, au). It supports encryption and passphrase protection to further secure the hidden data.

   **Basic Commands**:
   - **Embed Data**:
     ```bash
     steghide embed -cf [cover_file] -ef [secret_file] -p [password]
     ```
   - **Extract Data**:
     ```bash
     steghide extract -sf [stego_file] -p [password]
     ```

---
# CTF Forensics and Steganography Challenges

## Overview

This repository is focused on **Forensics** and **Steganography** challenges often encountered in Capture The Flag (CTF) competitions. These challenges require participants to analyze digital evidence, recover hidden data, and solve puzzles by using a wide variety of tools and techniques.

---

## Forensics in CTF

**Forensics** is the art of recovering the digital trail left behind on a computer system. In CTFs, forensic challenges often require participants to analyze files, memory dumps, network traffic, or logs to uncover hidden information or reconstruct events.

### Types of Forensics Challenges:

1. **File Analysis**: Examine disk images, memory dumps, log files, or network captures for hidden information.
2. **Steganography**: Detect and extract data hidden in images, audio, or other files.
3. **Network Forensics**: Analyze packet captures (PCAP files) to recover data or trace malicious activity.
4. **Memory Forensics**: Analyze volatile memory to uncover processes, network connections, or artifacts left by malware.
5. **Log Analysis**: Review log files from web servers, firewalls, and intrusion detection systems.

---

## Common Forensics Tools and Commands

### Initial Analysis:
- `strings [file]`: Search for readable strings within a file.
- `grep [pattern] [file]`: Search for a specific pattern in a file.
- `bgrep`: Search for non-text patterns in binary files.
- `hexdump -C [file]`: View the contents of a file in hexadecimal format.

### File Formats:
You may encounter various file formats during forensic challenges, such as:
- Archive files (ZIP, TGZ)
- Image files (JPG, PNG, BMP)
- Packet captures (PCAP, PCAPNG)
- Office documents (RTF, OOXML)
  
### File Signatures:
Files often contain specific leading bytes called **file signatures** or **magic numbers** that identify their format. Use a hex editor to view these bytes and compare them with known signatures.

### Encodings:
In many challenges, data may be encoded. For example, **Base64** is easily recognized by its alphanumeric characters and “=” padding. Example:

```bash
echo aGVsbG8gd29ybGQh | base64 -D
# Output: hello world!



