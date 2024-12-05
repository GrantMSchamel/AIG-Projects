# 🛡️ Bypassing Ransomware Encryption: Bruteforce Decryption Key

---

## **Challenge Scenario**

### **Introduction**  
Following the Apache Log4j vulnerability incident, AIG's Incident Detection & Response team successfully mitigated a ransomware attack. However, the attack encrypted one zip file, and the decryption key remains locked. The Chief Information Security Officer (CISO) has decided against paying the ransom, opting to break the encryption through brute-forcing instead.

Your task is to use a brute-force approach to recover the encryption key for the affected file. You will leverage a widely known password wordlist, Rockyou, and write a Python script to iterate over potential passwords to decrypt the encrypted zip file.

---

## **⚠️ Disclaimer**  
This task simulates a real-world ransomware decryption challenge where brute-forcing is used to recover an encrypted file without paying the ransom. The Python code provided is part of the solution framework, which will require customization to meet the task requirements.

---

## **🛠️ Task Objectives**

1. **Write a Python script to brute-force the decryption key.**
2. **Leverage the provided Rockyou wordlist for password attempts.**
3. **Ensure the script can identify the correct password and extract the file.**

---

## **📚 Research Summary: Brute-Forcing Ransomware Encryption**

Brute-forcing ransomware encryption involves repeatedly trying a list of possible passwords until the correct one is found. In this case, the password is likely to be a weak one, as the attacker did not employ sophisticated encryption strategies.

The provided resources include:
- **Rockyou.txt**: A wordlist containing thousands of common passwords.
- **Python Template**: A starter script to handle the bruteforce process.

Ransomware often uses weak or common passwords, making brute-forcing a viable strategy for decryption. The Python script attempts each password until the correct one is found, allowing the encrypted zip file to be extracted.

---

## **📝 Python Bruteforce Script for Decrypting Ransomware Zip File**

```python
from zipfile import ZipFile

# Use a method to attempt to extract the zip file with a given password
def attempt_extract(zf_handle, password):
    try:
        zf_handle.extractall(pwd=password)
        print(f"[+] Password found: {password}")
        return True #returns true if password was found
    except RuntimeError:
        return False

def main():
    print("[+] Beginning bruteforce ")

    with ZipFile('enc.zip') as zf:
        with open('rockyou.txt', 'rb') as f:
            # Iterate through password entries in rockyou.txt
            for line in f:
                password = line.strip()
                print(f"[-] Trying password: {password}")

                # Attempt to extract the zip file using each password
                if attempt_extract(zf, password):
                    break

    print("[+] Password not found in list")

if __name__ == "__main__":
    main()
```

---

## **How the Script Works**

- **`attempt_extract` Function**: Tries to extract the contents of the encrypted zip file using a given password.
- **Main Function**: Iterates through each password in the `rockyou.txt` wordlist, attempting to extract the zip file.
- **Output**: If the correct password is found, it will print the message `[+] Password found: <password>`. If not, it will notify that the password was not found in the list.

---

## **🧠 Key Takeaways**

- **Brute-Forcing**: This approach is useful when dealing with weak encryption or poorly chosen passwords.
- **Python Scripting**: Python provides a simple and effective tool for automating tasks like password cracking.
- **Wordlists**: Using precompiled wordlists like Rockyou increases the chances of finding common passwords quickly.

By using brute-forcing techniques, we can recover the encrypted file without paying the ransom, saving both time and resources.
