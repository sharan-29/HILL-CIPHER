# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```python
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int key[3][3];

void encrypt(char text[])
{
    int n = strlen(text);
    for(int i=0;i<n;i+=3) {
        int p[3]={0}, c[3]={0};
        for(int j=0;j<3;j++) {
            if(i+j<n) p[j] = toupper(text[i+j])-'A';
            else p[j] = 'X'-'A'; 
        }
        for(int r=0;r<3;r++) {
            for(int k=0;k<3;k++)
                c[r] += key[r][k]*p[k];
            c[r]%=26;
        }
        for(int j=0;j<3;j++)
            printf("%c", c[j]+'A');
    }
}

int main() {
    char text[100];
    printf("Enter plain text: ");
    scanf("%s", text);

    printf("Enter 3x3 key matrix (row-wise):\n");
    for(int i=0;i<3;i++)
        for(int j=0;j<3;j++)
            scanf("%d",&key[i][j]);

    printf("Cipher Text: ");
    encrypt(text);

    return 0;
}
```
## OUTPUT

<img width="1917" height="873" alt="image" src="https://github.com/user-attachments/assets/c1abd630-2c8b-48d1-89e6-70aa3f74d672" />


## RESULT

Thus The Program Has Been Successfully Initiated

