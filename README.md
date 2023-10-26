# CryptLFSR - Command Line Images Encryption

<div style="display: flex; justify-content: space-around; align-items: center;">
  <img src="img/decrypted.ppm" alt="Pixel art of a city"/>
  <img src="img/encrypted.ppm" alt="Encrypted of the pixel art of a city, noisy image"/>
</div>

Command line program made to encrypt images of type PNM (PBM · PGM · PPM)
The encrpytion is do using LFSR techniques (XOR encryption), see : [https://en.wikipedia.org/wiki/Linear-feedback_shift_register]

# Table of Contents
1. [Setup](#setup)
2. [Parameters](#parameters)
3. [Forbidden file name](#forbidden-file-name-for--o)
4. [Usage example](#usage)
5. [Documentation](#documentation)
6. [Used libraries](#used-libraries)
7. [Future improvements](#future-improvements)

## Setup
- Install gcc ([https://gcc.gnu.org/install/])

- Clone the repository
```console
    git clone locationOfTheprogram
```
- Go to the folder of the projet
```console
cd locationOfTheprogram
```
- Run the ```make``` command at the root of the directory
```console
make
```

## Parameters
All parameters are mandatory
-`-i`: the path of the image you want to encrypt / decrypt
-`-o`: the path for the encrypted/decrypted image, can not contain `/\\:*?\"<>|`
-`-p`: a password (e.g., myPassword@!)
-`-t`: the tap value for the LFSR encryption (see : [https://en.wikipedia.org/wiki/Linear-feedback_shift_register])

## Forbidden file name for -o
A file name can not contain any of the following character : `/\\:*?\"<>|`

## Usage example
Encrypt an image using password "secretpassword123"
```console
make
```
```console
./CryptLFSR -i img/city.ppm -o city_encrypted.ppm -p veryGoodPassword -t 5
```

Decrypt the image using the encryption password 
```console
./CryptLFSR -i city_encrypted.ppm -o city_decrypted.ppm -p veryGoodPassword -t 5
```

## Documentation
Run the command
```console
make doc
```
Then open doc/html/index.html
```console
open doc/html/index.html
```

## Used libraries
- Seatest : [https://code.google.com/archive/p/seatest/]

## Future improvements <a id="futurimprov"></a>
- Multithreading for the processing of the pixels matrix