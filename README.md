# PRODIGY_CS_01
# Implement Caesar Cipher
def encrypt(text, shift):
    result = ""

    # traverse text
    for i in range(len(text)):
        char = text[i]

        # Encrypt uppercase characters
        if char.isupper():
            result += chr((ord(char) + shift - 65) % 26 + 65)
        # Encrypt lowercase characters
        elif char.islower():
            result += chr((ord(char) + shift - 97) % 26 + 97)
        else:
            result += char  # Non-alphabetic characters remain unchanged

    return result

def decrypt(text, shift):
    return encrypt(text, -shift)

def main():
    print("Caesar Cipher Program")
    choice = input("Do you want to (E)ncrypt or (D)ecrypt? ")

    if choice.lower() not in ['e', 'd']:
        print("Invalid choice! Please select either E for Encrypt or D for Decrypt.")
        return

    text = input("Enter your message: ")
    shift = int(input("Enter the shift value: "))

    if choice.lower() == 'e':
        encrypted_text = encrypt(text, shift)
        print(f"Encrypted Text: {encrypted_text}")
    else:
        decrypted_text = decrypt(text, shift)
        print(f"Decrypted Text: {decrypted_text}")

if __name__ == "__main__":
    main()
