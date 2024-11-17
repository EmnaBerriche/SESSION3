# SESSION2
# CTF Cybersecurity Workshop: Steganography &amp; Forensics
# Intro to Steganography

## Description

**Steganography** is a technique used to conceal secret information within an ordinary file or message, in such a way that it avoids detection. The hidden data can be in the form of text, image, video, or audio, and is often encrypted before being embedded into the cover medium to enhance security. Steganography can be used for both constructive purposes (like secure communications) and destructive purposes, including cyber-attacks known as **Stegware**.

---

## LSB Steganography

**LSB (Least Significant Bit) Steganography** is a method of hiding information within digital images, audio, or other media by altering the least significant bits of each pixel or sample.

- **Pixels in Images**: In an image, each pixel is made up of RGB (red, green, blue) values. Each of these values ranges from 0 to 255, which can be represented in 8 bits. By changing the least significant bits, you can embed secret information without visibly altering the image.
  ![LSB](IMAGES/lsb.png)
- **Audio Samples in .wav Files**: In audio steganography, the LSB of audio samples can be changed to hide data, similar to how pixel values are altered in images.

### Tools for LSB Steganography

1. **StegOnline (georgeom.net)**  
   A web-based tool for LSB steganography in images. It allows users to choose the number of bits to modify (LSB or MSB) and the direction of data embedding.  
   [StegOnline](https://stegonline.georgeom.net/upload)

2. **Steghide**  
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

3. **Stegolsb**  
   A tool specifically designed for embedding and extracting hidden data from `.wav` files using LSB techniques. By modifying the LSB of audio samples, data can be hidden without noticeably affecting the sound quality.

4. **Stegsnow**  
   A tool for **whitespace steganography**, where messages are concealed using white spaces at the end of lines in a text file. Even if the whitespace pattern is detected, the use of encryption can prevent the message from being easily deciphered.

---

## Examples

### Image Steganography with Steghide

- **Embedding Data in an Image**:
   ```bash
   steghide embed -cf example.jpg -ef secret.txt -p mypassword


