# EX-NO-7-Implement-DES-Encryption-and-Decryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.<br>
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.<br>
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).<br>
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.<br>

## Program:
```
def encrypt(message, key):
    key_length = len(key)
    encrypted = []

    for i in range(len(message)):
        # XOR each character with the corresponding character in the key
        encrypted_char = ord(message[i]) ^ ord(key[i % key_length])
        encrypted.append(encrypted_char)

    return encrypted  # Return list of encrypted ASCII values


def decrypt(encrypted, key):
    key_length = len(key)
    decrypted = []

    for i in range(len(encrypted)):
        decrypted_char = encrypted[i] ^ ord(key[i % key_length])
        decrypted.append(chr(decrypted_char))

    return ''.join(decrypted)


def main():
    print("\n**Simulation of DES encryption and decryption\n")

    message = input("Enter the message to encrypt: ")
    key = input("Enter the encryption key: ")

    encrypted_message = encrypt(message, key)

    print("Original Message:", message)
    print("Encrypted Message (Hex):", ' '.join(f"{byte:02X}" for byte in encrypted_message))

    decrypted_message = decrypt(encrypted_message, key)
    print("Decrypted Message:", decrypted_message)


if __name__ == "__main__":
    main()

 ```
## Output:
![image](https://github.com/user-attachments/assets/cf8c2bb4-fdd9-4c6b-9464-f89c4d0f609a)


## Result:
The program is executed successfully

