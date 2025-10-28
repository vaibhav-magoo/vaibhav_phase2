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

- found this video explaining the bmp file structure. [youtube video]([https://google.com](https://www.youtube.com/watch?v=13E0il2zxBA&list=WL&index=1))


***

