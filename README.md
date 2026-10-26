# EX-NO-3-IMPLEMENTATION-OF-HILL-CIPHER
Implementation of the Hill Cipher substitution technique using C programming for the Cryptography laboratory experiment.

## Name: Arunachalam.M
## Reference Number: 212225230019

# Aim:
To write a C program to implement the Hill Cipher substitution technique for encrypting plaintext using a 3 × 3 key matrix.

# Algorithm:
1. Read the plaintext and the 3 × 3 key matrix from the user.

2. Convert each letter of the plaintext into its corresponding numerical value (A = 0, B = 1, …, Z = 25).

3. Divide the plaintext into groups of three letters.

4. If necessary, append the letter X to make the plaintext length a multiple of three.

5. Multiply each group by the key matrix using modulo 26 arithmetic.

6.Convert the resulting numerical values into letters to obtain the ciphertext.

7.Display the encrypted ciphertext.

# Program:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char text[100];
    int key[3][3], i, j, k;
    int len, a, b, c;

    printf("Enter plaintext (uppercase, no spaces): ");
    scanf("%99s", text);

    printf("Enter 3x3 key matrix:\n");
    for (i = 0; i < 3; i++)
        for (j = 0; j < 3; j++)
            scanf("%d", &key[i][j]);

    len = strlen(text);

    while (len % 3 != 0)
        text[len++] = 'X';
    text[len] = '\0';

    printf("Ciphertext: ");

    for (i = 0; i < len; i += 3)
    {
        a = toupper(text[i]) - 'A';
        b = toupper(text[i + 1]) - 'A';
        c = toupper(text[i + 2]) - 'A';

        for (j = 0; j < 3; j++)
        {
            k = (key[j][0] * a +
                 key[j][1] * b +
                 key[j][2] * c) % 26;

            printf("%c", k + 'A');
        }
    }

    printf("\n");
    return 0;
}
```
# Output:

<img width="1235" height="275" alt="image" src="https://github.com/user-attachments/assets/0ed2ec0c-215c-4b56-b8f4-3abb4f2c70f0" />

# Result:
Thus, the C program to implement the Hill Cipher substitution technique was successfully executed, and the plaintext was encrypted into ciphertext using a 3 × 3 key matrix and modulo 26 arithmetic.
