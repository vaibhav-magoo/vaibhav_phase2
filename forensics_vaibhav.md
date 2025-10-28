# 1. m00nwalk

> Decode this message from the moon.

## Solution:

- used the hint to find out that apollo 11 used SSTV signals
- used an online sstv decoder to decode this signal
- found an image with the flag in it

<img width="1905" height="897" alt="image" src="https://github.com/user-attachments/assets/8f2ea71a-bff2-4628-a2e3-3afb1f75594d" />


## Flag:

```
picoCTF{beep_boop_im_in_space}
```


## Resources:

- how images were sent back from the moon landing [quora post]([https://google.com](https://www.quora.com/How-did-they-manage-to-broadcast-live-to-television-from-the-moon-50-years-ago-weight-of-equipment-energy-needed-size-of-the-antenna))


# 2. tunn3l v1s10n

> We found this file. Recover the flag.

## Solution:

- opened the file with hexedit
- identified the file format as BMP
 <img width="640" height="196" alt="Screenshot 2025-10-27 184926" src="https://github.com/user-attachments/assets/f808da31-e026-44a5-9628-896386aad92a" />
 
- crosschecked the file headers with another BMP file
- first the bits that handle the begining of the pixel data were too big so i changed it to 36 
- the size of the bmih header was wrong as well
- tried viewing the image now and found a false flag
 <img width="1458" height="846" alt="image" src="https://github.com/user-attachments/assets/84d4566a-4385-4d6e-8b29-bfeba6010bc0" />
 
- tried messing with the image dimensions for a bit and finally found it
  <img width="1457" height="701" alt="image" src="https://github.com/user-attachments/assets/c2c9071c-ff97-4e87-8d63-bee463a81edd" />



## Flag:

```
picoCTF{qu1t3_a_v13w_2020}
```

## Concepts learnt:

- learnt little endian and big endian order
- bitmap files use little endian ordering
- learn the structure of bitmap files

## Notes:

- spent a lot of time looking for steganography in the image.
- 

## Resources:

- found this video explaining the bmp file structure. [youtube video](https://www.youtube.com/watch?v=13E0il2zxBA&list=WL&index=1)


***

# 2. Trivial Flag Transfer Protocol

> Figure out how they moved the flag.

## Solution:

- downlaoded the file and opened with wireshark
- there were tftp protocols 
- filtered the tftp packets
- and then exported all of them
  <img width="993" height="981" alt="image" src="https://github.com/user-attachments/assets/afccb054-f437-405a-b79d-b74273e4e42e" />
- examined the instructions.txt file
- figured out it was a ROT13 cipher
  <img width="907" height="902" alt="image" src="https://github.com/user-attachments/assets/b3a7b732-3c21-4da0-a628-f8831eb6a619" />
- there was more rot13 in the plan file
- decoding this gave: I USED THE PROGRAM AND HID IT WITH-DUEDILIGENCE. CHECKOUT THE PHOTOS
- figured out the file was for steghide
- after some trial and error got the flag.txt file using steghide and the password was steghide
- got the flag




## Flag:

```
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
```

## Concepts learnt:

- filtering specific protocols in wireshark
- solving ROT13 ciphers

***



