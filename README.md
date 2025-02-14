# DrCrypt - Python Encryption Library

![PyPI](https://img.shields.io/pypi/v/drcrypt)
![License](https://img.shields.io/pypi/l/drcrypt)

DrCrypt is a Python encryption library that provides various cryptographic functions for your projects. It aims to simplify encryption tasks and provide a user-friendly interface for common encryption algorithms.

## Installation

You can install `DrCrypt` using pip:

```bash
pip install drcrypt
```

## Features

- Easy-to-use API for common encryption tasks.
- Supports various encryption algorithms, including MD5, SHA-256, SHA-3, and more.
- Provides functions for generating random strings and hashes.
- Well-documented and user-friendly interface.

## Usage

### XOR Encryption

Here's a quick example of how to use `DrCrypt` to perform XOR encryption:

```python
from drcrypt.crypt import XOR

text = "Hello, World"
xor = XOR("MyPassword", "utf-8")
en = xor.encrypt(text)

print("Text:", text, end="\n\n")
print("Encrypt:", en)
print("Decrypt:", xor.decrypt(en))
```

In the provided code snippet, the `XOR` class from the `drcrypt.crypt` module is imported. The example demonstrates how to use the XOR encryption feature of `DrCrypt`. It encrypts the given text using the XOR cipher and a provided password. The encrypted text is then printed, followed by decrypting it using the same password and printing the decrypted result.

### AES Encryption and Decryption

Here's a simple example of how to use `DrCrypt` to perform AES encryption and decryption:

```python
from drcrypt.crypt import encrypt_aes, decrypt_aes

key = "MyTestPassword!!".encode("utf-8")
text = "Hello, world"
en = encrypt_aes(text, key)

print("Text:", text, end="\n\n")
print("Encrypted:", en.decode("utf-8"))
print("Decrypted:", decrypt_aes(en, key).decode("utf-8"))
```

In the provided code snippet, the `encrypt_aes` and `decrypt_aes` functions from the `drcrypt.crypt` module are imported. This example demonstrates how to use `DrCrypt` to encrypt and decrypt data using the Advanced Encryption Standard (AES) algorithm. It encrypts the given text using the provided key, prints the original text, the encrypted result, and then decrypts the encrypted text using the same key and prints the decrypted result.

### Hashing

Here's a simple example of how to use `DrCrypt` to generate an SHA-1 hash:

```python
from drcrypt.hash import SHA1

data = "Hello, SHA-1!"
sha1_hash = SHA1()
sha1_hash.update(data.encode("utf-8"))
sha1_hash.finalize()
hashed = sha1_hash.hexdigest()

print("Data:", data)
print("SHA-1 Hash:", hashed)
```

In the provided code snippet, the `SHA1` class from the `drcrypt.hash` module is imported. This example demonstrates how to use `DrCrypt` to compute the SHA-1 hash of a given string (`data`). It initializes the SHA-1 hash object, updates it with the data, finalizes the hash computation, and then prints the original data and its corresponding SHA-1 hash.

Here's a simple example of how to use `DrCrypt` to generate an SHA-256 hash:

```python
from drcrypt.hash import SHA256

data = "Hello, SHA-256!"
sha256_hash = SHA256()
sha256_hash.update(data.encode("utf-8"))
sha256_hash.finalize()
hashed = sha256_hash.hexdigest()

print("Data:", data)
print("SHA-256 Hash:", hashed)
```

In the provided code snippet, the `SHA256` class from the `drcrypt.hash` module is imported. This example demonstrates how to use `DrCrypt` to compute the SHA-256 hash of a given string (`data`). It initializes the SHA-256 hash object, updates it with the data, finalizes the hash computation, and then prints the original data and its corresponding SHA-256 hash.

Here's a simple example of how to use `DrCrypt` to generate an MD5 hash:

```python
from drcrypt.hash import MD5

data = "Hello, MD5!"
md5_hash = MD5()
md5_hash.update(data.encode("utf-8"))
md5_hash.finalize()
hashed = md5_hash.hexdigest()

print("Data:", data)
print("MD5 Hash:", hashed)
```

In the provided code snippet, the `MD5` class from the `drcrypt.hash` module is imported. This example demonstrates how to use `DrCrypt` to compute the MD5 hash of a given string (`data`). It initializes the MD5 hash object, updates it with the data, finalizes the hash computation, and then prints the original data and its corresponding MD5 hash.

### Comparing Hashes

Here's an example of how to use `DrCrypt` to compute and compare MD5 hashes:

```python
from drcrypt.hash import MD5
from drcrypt import compare_hash

data = "Hello, MD5!"
md5_hash = MD5()
md5_hash.update(data.encode("utf-8"))
md5_hash.finalize()
hashed = md5_hash.hexdigest()

result = compare_hash(MD5(), data, hashed)

if result:
    print("Hashes match! The data matches the target hash.")
else:
    print("Hashes do not match. The data does not match the target hash.")
```

In the provided code snippet, the `MD5` class from the `drcrypt.crypt` module is used to compute an MD5 hash for a given string (`data`). The `compare_hash` function is then used to compare the computed hash with the target hash (`hashed`). The example demonstrates how to verify whether the data matches the target hash and prints a corresponding message.

### Secure Password Hashing and Verification

Here's an example of how to use the `Bcrypt` class from `DrCrypt` to perform secure password hashing and verification:

```python
from drcrypt.hash import Bcrypt

# Create an instance of Bcrypt
bcrypt_hasher = Bcrypt()

# Hash a password and generate a salt
password = "mysecretpassword"
salt = bcrypt_hasher.generate_salt()
hashed_password = bcrypt_hasher.bcrypt_hash(password, salt)

# Verify an entered password
input_password = "mysecretpassword"
if bcrypt_hasher.verify_password(input_password, hashed_password):
    print("Password Matched!")
else:
    print("Password Does Not Match!")
```

In the provided code snippet, the `

Bcrypt` class from the `drcrypt.hash` module is used. This example demonstrates how to use `DrCrypt` to securely hash and verify passwords using the bcrypt algorithm. It creates an instance of the `Bcrypt` class, hashes a password with a generated salt, and then verifies an entered password against the hashed password.

### Generating Random Numbers and Strings

Here's an example of how to use the `Random` class from `DrCrypt` to generate random numbers and strings:

```python
from drcrypt import Random

# Create an instance of Random
r = Random()

# Generate a random integer between 1 and 10
random_int = r.randint(1, 10)
print("Random Integer:", random_int)

# Generate a random string with characters "AaBbCcDd1234567890" and length 10
random_str = r.randstr(10, "AaBbCcDd1234567890")
print("Random String:", random_str)
```

In the provided code snippet, the `Random` class from the `drcrypt.random` module is used. This example demonstrates how to use `DrCrypt` to generate random numbers and strings. It creates an instance of the `Random` class and then generates a random integer within the specified range and a random string with the specified characters and length.

## Documentation

For detailed documentation and examples, please refer to the [official documentation](#).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
