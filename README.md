# COEP CyberCell Mini CTF 2026 – My CTF Solution

## Introduction

This repository contains my write-up for the COEP CyberCell Induction CTF 2026.

The purpose of this write-up is to document the challenges I solved, the techniques I learned, and the reasoning used to obtain the flags.

---

## Challenge 1 – Nothing to See Here

### Category
Web Source

### Objective
Find the hidden flag in the webpage.

### Solution

The challenge suggested that there was something hidden in the webpage.

I opened the webpage source using:

`Ctrl + U`

While inspecting the HTML source code, I found a comment containing the flag.

### Flag

`COEP{view_source_is_your_friend}`

### What I learned

I learned that HTML comments and webpage source code can contain information that is not visible on the rendered webpage.

---

## Challenge 2 – Mystery String

### Category
Cryptography

### Objective
Decode the given string.

### Solution

The challenge provided an encoded string:

`Q09FUHtiYXN1NjRfaXNfbm90X2VuY3J5cHRpb259`

I recognized that it looked like Base64 encoding.

After decoding it, I obtained the flag.

### Flag

`COEP{basu64_is_not_encryption}`

### What I learned

I learned the difference between encoding and encryption. Base64 is an encoding scheme and does not provide encryption or security.

---

## Challenge 3 – Picture Perfect

### Category
Forensics

### Objective
Find hidden information in an image.

### Solution

The challenge provided an image file and suggested inspecting its metadata and strings.

I learned that image files can contain metadata such as EXIF information.

Tools/commands that can be used for this type of analysis include:

`exiftool photo.jpg`

and

`strings photo.jpg`

The relevant information revealed the flag.

### Flag

`COEP{metadata_never_lies}`

### What I learned

I learned that metadata can contain useful information during digital forensics investigations.

---

## Challenge 4 – Polite Robots

### Category
Web Recon

### Objective
Investigate the website's robots.txt file.

### Solution

I checked the website's `robots.txt` file.

The file contained disallowed paths, including a suspicious directory.

Following the relevant path led to the hidden flag.

### Flag

`COEP{robots_know_secrets}`

### What I learned

I learned that robots.txt is normally used to provide crawling instructions to search engine bots, but it can sometimes reveal interesting paths or directories.

---

## Challenge 5 – Where Was This Taken?

### Category
OSINT

### Objective
Identify the historic building shown in the image.

### Solution

The clues described a historic COEP campus building with a stone facade and clock tower.

I researched the clues and identified the building as the historic Main Building of COEP.

### Flag

`COEP{main_building}`

### What I learned

I learned how OSINT can be used to identify a location by combining visual clues, historical information, and publicly available sources.

---

## Challenge 6 – Not What It Seems

### Category
File Forensics

### Objective
Identify the true type of a suspicious file.

### Solution

The file was named:

`mystery.jpg`

However, the challenge explained that file extensions cannot always be trusted.

The first bytes of the file were:

`50 4B 03 04`

These are the magic bytes associated with a ZIP archive.

Therefore, although the file had a `.jpg` extension, its actual format was a ZIP archive.

I changed the extension to `.zip`, extracted the archive, and found `flag.txt`.

The flag was obtained from the extracted file.

### Flag

`COEP{not_every_jpg_is_a_jpg}`

### What I learned

I learned about magic bytes and file signatures. A file's extension does not necessarily indicate its true format.

---

# AI Usage Disclosure

I used AI tools as a learning and research assistant during this CTF.

I used AI to:

- Understand challenge clues.
- Learn about Base64 encoding.
- Understand HTML source inspection.
- Understand robots.txt.
- Understand file signatures and magic bytes.
- Troubleshoot the extraction of the disguised ZIP file.
- Improve the organization and explanation of this write-up.

I independently followed the instructions, inspected the challenge artifacts, and verified the results while solving the challenges.

The AI was used as an educational assistant and not as a replacement for understanding the techniques used.

---

# Overall Learning

Through these challenges, I learned basic techniques from:

- Web Source Inspection
- Encoding
- Digital Forensics
- Web Reconnaissance
- OSINT
- File Signatures and Magic Bytes

This CTF helped me understand how small clues in webpages, files, metadata, and public information can be combined to solve cybersecurity problems.
