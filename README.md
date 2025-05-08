# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:

```

#include <stdio.h>
#include <string.h>

void xor_encrypt_decrypt(char *input, const char *key) {
    int input_len = strlen(input);
    int key_len = strlen(key);
    for (int i = 0; i < input_len; i++) {
        input[i] ^= key[i % key_len];
    }
}

int main() {
    char input[256];
    char key[256];

    // Get text input from user
    printf("Enter text to encrypt: ");
    fgets(input, sizeof(input), stdin);
    input[strcspn(input, "\n")] = '\0';  // Remove newline character

    // Get key input from user
    printf("Enter encryption key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';  // Remove newline character

    // Show original input
    printf("\nOriginal text: %s\n", input);

    // Encrypt
    xor_encrypt_decrypt(input, key);
    printf("Encrypted text (raw may look garbled): %s\n", input);
    printf("Encrypted text (hex): ");
    for (int i = 0; i < strlen(input); i++) {
        printf("%02X ", (unsigned char)input[i]);
    }
    printf("\n");

    // Decrypt
    xor_encrypt_decrypt(input, key);
    printf("Decrypted text: %s\n", input);

    return 0;
}

```

# OUTPUT:

![image](https://github.com/user-attachments/assets/145a1c3f-d5c1-4048-8c51-0c972285e065)



# RESULT:

Thus code for Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption is executed successfully.

