# HILL CIPHER
HILL CIPHER
# EX. NO: 3 
# AIM:
    
To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user.

STEP-2: Split the plain text into groups of length three.

STEP-3: Arrange the keyword in a 3*3 matrix.

STEP-4: Multiply the two matrices to obtain the cipher text of length three.

STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main()
{
    char plaintext[100];
    int key[3][3];
    int pt[3], ct[3];
    int i, j, k, len;
    printf("Enter the plaintext: ");
    scanf("%s", plaintext);
    for(i = 0; i < strlen(plaintext); i++)
    {
        plaintext[i] = toupper(plaintext[i]);
    }
    printf("Enter the 3x3 key matrix (row-wise):\n");
    for(i = 0; i < 3; i++)
    {
        for(j = 0; j < 3; j++)
        {
            scanf("%d", &key[i][j]);
        }
    }
    len = strlen(plaintext);
    while(len % 3 != 0)
    {
        plaintext[len++] = 'X';
        plaintext[len] = '\0';
    }

    printf("\nCipher Text/Enctpted Text: ");
    for(i = 0; i < len; i += 3)
    {
        for(j = 0; j < 3; j++)
        {
            pt[j] = plaintext[i + j] - 'A';
        }
        for(j = 0; j < 3; j++)
        {
            ct[j] = 0;
            for(k = 0; k < 3; k++)
            {
                ct[j] += key[j][k] * pt[k];
            }
            ct[j] = ct[j] % 26;
        }
        for(j = 0; j < 3; j++)
        {
            printf("%c", ct[j] + 'A');
        }
    }
}
```

## OUTPUT
<img width="315" height="202" alt="image" src="https://github.com/user-attachments/assets/85175c97-e7df-49c6-889f-cdbb54816801" />


## RESULT

Thus the Hill Cipher is implemented succesfuuly
