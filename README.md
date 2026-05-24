# EX-NO-13-MESSAGE-AUTHENTICATION-CODE-MAC

## AIM:
To implement MESSAGE AUTHENTICATION CODE(MAC)

NAME:AVANTHIKA.M


REG NO:212224110009

## ALGORITHM:

1. Message Authentication Code (MAC) is a cryptographic technique used to verify the integrity and authenticity of a message by using a secret key.

2. Initialization:
   - Choose a cryptographic hash function \( H \) (e.g., SHA-256) and a secret key \( K \).
   - The message \( M \) to be authenticated is input along with the secret key \( K \).

3. MAC Generation:
   - Compute the MAC by applying the hash function to the combination of the message \( M \) and the secret key \( K \): 
     \[
     \text{MAC}(M, K) = H(K || M)
     \]
     where \( || \) denotes concatenation of \( K \) and \( M \).

4. Verification:
   - The recipient, who knows the secret key \( K \), computes the MAC using the received message \( M \) and the same hash function.
   - The recipient compares the computed MAC with the received MAC. If they match, the message is authentic and unchanged.

5. Security: The security of the MAC relies on the secret key \( K \) and the strength of the hash function \( H \), ensuring that an attacker cannot forge a valid MAC without knowledge of the key.

## Program:
```
MAC_SIZE = 16

def compute_mac(key, message):
    mac = ""

    for i in range(MAC_SIZE):
        value = ord(key[i % len(key)]) ^ ord(message[i % len(message)])
        mac += format(value, '02x')

    return mac


key = input("Enter secret key: ")
message = input("Enter message: ")

mac = compute_mac(key, message)

print("Generated MAC:", mac)

received = input("Enter received MAC: ")

if mac == received:
    print("MAC Verification Successful")
else:
    print("MAC Verification Failed")
```





## Output:

<img width="1424" height="863" alt="Screenshot 2026-05-24 113221" src="https://github.com/user-attachments/assets/f7bd95a9-3121-4dbb-a94b-49ea1c6ab633" />




## Result:
The program is executed successfully.
