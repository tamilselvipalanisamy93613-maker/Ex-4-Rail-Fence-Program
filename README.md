# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
#include <stdio.h>
#include <string.h>

int main()
{
    char text[100];
    int rail, len, i, j, dir;

    printf("Enter the plaintext: ");
    scanf("%s", text);

    printf("Enter the number of rails: ");
    scanf("%d", &rail);

    len = strlen(text);

    char fence[rail][len];

    for(i = 0; i < rail; i++)
        for(j = 0; j < len; j++)
            fence[i][j] = '\n';

    int row = 0;
    dir = 1;

    for(i = 0; i < len; i++)
    {
        fence[row][i] = text[i];

        if(row == rail - 1)
            dir = -1;
        else if(row == 0)
            dir = 1;

        row += dir;
    }

    printf("\nCipher Text: ");

    for(i = 0; i < rail; i++)
        for(j = 0; j < len; j++)
            if(fence[i][j] != '\n')
                printf("%c", fence[i][j]);

    return 0;
}
```
# OUTPUT
<img width="1642" height="642" alt="image" src="https://github.com/user-attachments/assets/4a0a5482-c5ef-4721-b39a-30c4f3574248" />

# RESULT
Thus, the C program to implement the Rail Fence Transposition Technique was successfully executed, and the corresponding cipher text was generated.
