
# EncryptionHelper for C#

This guide provides instructions for using the `EncryptionHelper` class to encrypt and decrypt strings in C#. The class utilizes the AES encryption algorithm to ensure secure handling of sensitive data.

## Features
- Encrypt a plaintext string.
- Decrypt a Base64-encoded ciphertext string.

---

## How to Use

### Step 1: Import and Setup
1. Copy the `EncryptionHelper` class into your project.
2. Use the constructor to initialize it with a **16-byte key** and a **16-byte IV**. These should be securely stored in production environments.

```csharp
string key = "1234567890123456"; // Example key (16 characters for AES-128)
string iv = "6543210987654321"; // Example IV (16 characters)

var encryptionHelper = new EncryptionHelper(key, iv);
```

---

### Step 2: Encrypt a String
Use the `Encrypt` method to convert a plaintext string into an encrypted Base64-encoded string.

```csharp
string plainText = "HelloWorld";
string encryptedText = encryptionHelper.Encrypt(plainText);

Console.WriteLine($"Encrypted: {encryptedText}");
```

---

### Step 3: Decrypt a String
Use the `Decrypt` method to convert an encrypted Base64-encoded string back to its plaintext form.

```csharp
string decryptedText = encryptionHelper.Decrypt(encryptedText);

Console.WriteLine($"Decrypted: {decryptedText}");
```

---

## Complete Example
```csharp
public class Program
{
    public static void Main()
    {
        // Example key and IV (use secure values in production)
        string key = "1234567890123456"; // 16 bytes
        string iv = "6543210987654321"; // 16 bytes

        var encryptionHelper = new EncryptionHelper(key, iv);

        string originalText = "HelloWorld";
        Console.WriteLine($"Original: {originalText}");

        string encryptedText = encryptionHelper.Encrypt(originalText);
        Console.WriteLine($"Encrypted: {encryptedText}");

        string decryptedText = encryptionHelper.Decrypt(encryptedText);
        Console.WriteLine($"Decrypted: {decryptedText}");
    }
}
```

---

## Notes
1. **Key and IV Security:** Ensure the `key` and `iv` are stored securely (e.g., configuration files, environment variables, or key vaults).
2. **Key Length:** The key must be 16, 24, or 32 bytes, matching the AES variant (AES-128, AES-192, AES-256).
3. **Error Handling:** Add exception handling to manage potential errors during encryption and decryption.
4. **Production Use:** Do not hard-code sensitive keys and IVs in production code. 

Enjoy using secure encryption in your C# projects!
```

---

## License
This code is provided as-is, without warranty. Feel free to use and modify it in your projects.
