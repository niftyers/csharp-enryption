using namespace Niftyers;

public class Program
{
    public static void Main()
    {
        string key = "1234567890123456"; // Example key (16 characters for AES-128)
        string iv = "6543210987654321"; // Example IV (16 characters)

        var encryptionHelper = new EncryptionHelper(key, iv);

        string originalWord = "HelloWorld";
        Console.WriteLine($"Original: {originalWord}");

        string encryptedWord = encryptionHelper.Encrypt(originalWord);
        Console.WriteLine($"Encrypted: {encryptedWord}");

        string decryptedWord = encryptionHelper.Decrypt(encryptedWord);
        Console.WriteLine($"Decrypted: {decryptedWord}");
    }
}
