# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

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
    char msg[] = "Yathin";
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
<img width="735" height="189" alt="image" src="https://github.com/user-attachments/assets/adab9a1b-3aad-4563-b246-4b7ac547d6cd" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
