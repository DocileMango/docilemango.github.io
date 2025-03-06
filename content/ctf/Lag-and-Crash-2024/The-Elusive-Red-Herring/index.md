+++
date = '2024-03-22T22:49:53+08:00'
draft = false
title = 'The Elusive Red Herring'
url = 'the-elusive-red-herring'
+++

# Lag and Crash 2024

## Forensics - The Elusive Red Herring
Flag: LNC24{d0nT_f4LL_4_r3d_h3rR1nG5!}

## Write Up
This is the challenge:

![](./Images/image1.png)

Installing the JPG file, this is what we see:

![](./Images/image2.png)

Doing `strings qrcode.jpg >> output.txt` and opening VSCode, we decided to search for LNC24{ and find this:

![](./Images/image3.png)

We find just a bunch of fake flags.

Next, we decided to do binwalk on the image to see if there is anything we can extract, and we did!

![](./Images/image4.png)

We looked inside what we extracted and found 2 zip files and 1 directory:

![](./Images/image5.png)

This is inside the 'red_herrings' directory:

![](./Images/image6.png)

Inside 1, 2, 3 and 5 are just images, but within 4 was a zip file that we decided to extract.

After extracting that file, a bunch of 'flag.txt' files were extracted.

So we decided to use this grep command: `grep -r -v "LNC24{A_f4k3_fL4g_"`

![](./Images/image7.png)

And we got the flag!