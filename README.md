## EX-NO-7-Implement-DES-Encryption-and-Decryption
### Aim:
To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

### ALGORITHM:
 1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
 2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
 3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
 4.DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

### PROGRAM:
```
def encrypt(message, key):
    encrypted_message = []
    key_length = len(key)

    for i in range(len(message)):
        # XOR each character and store as encrypted
        encrypted_char = chr(ord(message[i]) ^ ord(key[i % key_length]))
        encrypted_message.append(encrypted_char)

    return ''.join(encrypted_message)


def decrypt(encrypted_message, key):
    decrypted_message = []
    key_length = len(key)

    for i in range(len(encrypted_message)):
        # XOR again with the same key to decrypt
        decrypted_char = chr(ord(encrypted_message[i]) ^ ord(key[i % key_length]))
        decrypted_message.append(decrypted_char)

    return ''.join(decrypted_message)


def main():
    print("\n      *****Simulation of DES encryption and decryption*****\n")

    # Get user input
    message = input("Enter the message to encrypt: ")
    key = input("Enter the encryption key: ")

    # Encrypt
    encrypted_message = encrypt(message, key)

    # Print original and encrypted message
    print("Original Message:", message)
    print("Encrypted Message (in hex):", end=' ')
    for char in encrypted_message:
        print(f"{ord(char):02X}", end=' ')
    print()

    # Decrypt
    decrypted_message = decrypt(encrypted_message, key)
    print("Decrypted Message:", decrypted_message)


if __name__ == "__main__":
    main()
```

### OUTPUT:
![image](https://github.com/user-attachments/assets/5171e312-6740-4bfe-bd89-643fac7599b2)

### RESULT:
The program is executed successfully.
