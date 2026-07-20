### Exp:1 IMPLEMENTATION OF CAESER CIPHER
## AIM:
To encrypt and decrypt the given message by using Caeser Cipher encryption algorithm.

## ALGORITHM:
Calculate the length of the plaintext.
For each character in the plaintext:
a. Add the key to the character to get the cipher character.
b. If the result exceeds 'Z' for uppercase or 'z' for lowercase, subtract 26 to wrap within the alphabet.
Display the encrypted text.
For decryption, subtract the key from each character of the ciphertext.
a. If the result is less than 'A' for uppercase or 'a' for lowercase, add 26 to wrap within the alphabet.
Display the decrypted text.
## PROGRAM:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

void encode(char *str, int offset, char *result) {
    int i;
    int length = strlen(str);
    offset = offset % 26 + 26;
    
    for (i = 0; i < length; i++) {
        if (isalpha(str[i])) {
            if (isupper(str[i])) {
                result[i] = 'A' + (str[i] - 'A' + offset) % 26;
            } else {
                result[i] = 'a' + (str[i] - 'a' + offset) % 26;
            }
        } else {
            result[i] = str[i];
        }
    }
    result[length] = '\0'; 
}

void decode(char *str, int offset, char *result) {

    encode(str, 26 - (offset % 26), result);
}

int main() {
    char msg[] = "Hi Myself Bala From AI & DS Dept";
    char encoded[256];
    char decoded[256];
    
    printf("Simulation of Caesar Cipher\n");
    printf("Input message: %s\n", msg);
    
    encode(msg, 12, encoded);
    printf("Encoded message: %s\n", encoded);
    
    decode(encoded, 12, decoded);
    printf("Decoded message: %s\n", decoded);
    
    return 0;
}
```
## OUTPUT:
<img width="1920" height="1080" alt="Screenshot (690)" src="https://github.com/user-attachments/assets/855b498b-4076-41a6-851b-76bcb9a1f10a" />

## RESULT:
The program implementing the Caesar cipher for encryption and decryption has been successfully executed, and the results have been verified.
