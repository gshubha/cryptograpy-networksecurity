Simplified AES, RSA and Digital Signture generation and verification using python
--Shubham Gupta

This project is used to show a secure connection between a client and server where data is sent in an encrypted manner.
It includes implementation of AES, RSA and SHA-256 as Hash function.
It also requires the Web Socket programming to generate a local server between the server and the client on the local system.
# Libraries used are
import asyncio
import sys
import websockets
import threading
import numpy as np
import json
import hashlib

Detailed overview is discussed below.


## For RSA Implementation
The entered parameters p and q will be used to generate the public key (e, n) and private key (d, n) for the server and client using the generatekeypair().
The r_encrypt and r_decrypt functions are written in such a way such that they could handle the encryption and decryption for both the integer value and digest generated using SHA256.

Following functionare used:
 genertekeypair():
 It generate public and private key pair for givin prime number 'p' and 'q'.
 r_encrypt():
 This function is used to encrypt message using two input key and message. 
 r_decrypt():
 This function is used to decrypt message using two input key and message.
 also isprime() is used to check for prime.

Also hashlib is used to generate hexadecimal digest.
and then digest is used to generate digital signature.
now at server side this signature is decrypted and used to verify the signature. 

Also cipher key is encrypted at client side using public key recived from server and 
decrypted at server using private key of server to generate cipher key entered. 

## For Aes Implementation
To implement S-AES we use python and socket programming and create a client and a server file in which client enter plain text of 16 bit and a  key and by AES algorithm plain text is encrypted to generate cipher text  at client side now  by using socket will send the generated ciphertext to server , server receive the cipher text and decrypt it using AES algorithm. 

# Key Generation

The first step is to generate the sub-keys. This is called Key Generation or Key Expansion:

The input key, K, is split into 2 words, w0 and w1:
The function keyExp() is used to generate the key.

Sub2Nib() function is used  to apply S-Box substitution on nibbles using encryption S-Box 

# Message Encryption and Decryption using AES
In next step plaintext and key generated is passed to encrypt function for client and decrypt function for server and then the process carries as it requires to be for encrypt and decrypt function similarly.
The encryption goes for two rounds and returns ciphertext for Encryption and plaintext for decryption. All the mid functions prints the data as stated in the standard output file provided.

Plaintext and Original are same 

The decryption worked and signature is verified!

# flow of file run
*server.py
*client.py








