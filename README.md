# HILL CIPHER
HILL CIPHER
NAME: CHINTALA AMAN MONTY
REG: 212224040054
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
```

#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char text[100];
    int a=3, b=3, c=2, d=5;
    int det=9, inv=3, i, x, y, p, q;
    char enc[100];

    printf("Enter plain text (even number of letters): ");
    scanf("%99s", text);

    for(i=0; text[i]; i++)
        text[i] = toupper(text[i]) - 'A';

    int len = strlen(text);

    for(i=0; i<len; i+=2) {
        x = text[i];
        y = text[i+1];
        p = (a*x + b*y) % 26;
        q = (c*x + d*y) % 26;
        enc[i] = p;
        enc[i+1] = q;
    }
    enc[len] = '\0';

    printf("Encrypted text: ");
    for(i=0; i<len; i++)
        printf("%c", enc[i] + 'A');

    printf("\nDecrypted text: ");
    for(i=0; i<len; i+=2) {
        x = enc[i];
        y = enc[i+1];
        p = (inv * (5*x - 3*y + 2600)) % 26;
        q = (inv * (-2*x + 3*y + 2600)) % 26;
        printf("%c%c", p+'A', q+'A');
    }

    printf("\n");
    return 0;
}

```

## OUTPUT
<img width="888" height="622" alt="image" src="https://github.com/user-attachments/assets/dd4dc427-fa45-4635-a106-7dae5c198169" />


## RESULT
Thus the program is successfully executed.
