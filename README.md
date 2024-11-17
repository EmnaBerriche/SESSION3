# SESSION2
# CTF Forensics and Steganography Challenges# Intro to Steganography
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


## Forensics in CTF

**Forensics** is the art of recovering the digital trail left behind on a computer system. In CTFs, forensic challenges often require participants to analyze files, memory dumps, network traffic, or logs to uncover hidden information or reconstruct events.

## Common Forensics Tools and Commands

### Initial Analysis:
### 1. Search for Readable Strings in a File
The `strings` command extracts readable (ASCII) text from binary files. This is useful when you want to search for hidden messages or readable data within a binary file.

```bash
strings [file]

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



