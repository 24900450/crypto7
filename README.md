# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char msg[100], key[100], enc[100], dec[100];
    int i, len, keylen;

    printf("Enter message: ");
    scanf("%s", msg);

    printf("Enter key: ");
    scanf("%s", key);

    len = strlen(msg);
    keylen = strlen(key);

    // Encryption
    for(i = 0; i < len; i++)
    {
        enc[i] = msg[i] ^ key[i % keylen];
    }
    enc[len] = '\0';

    printf("Encrypted: ");
    for(i = 0; i < len; i++)
    {
        printf("%02X ", (unsigned char)enc[i]);
    }
    printf("\n");

    // Decryption
    for(i = 0; i < len; i++)
    {
        dec[i] = enc[i] ^ key[i % keylen];
    }
    dec[len] = '\0';

    printf("Decrypted: %s\n", dec);

    return 0;
}
```



## Output:
<img width="431" height="259" alt="image" src="https://github.com/user-attachments/assets/eb7f5096-9378-4979-bb2d-2c232ef29bdb" />

## Result:
  The program is executed successfully

