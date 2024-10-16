# Ex--14---Hash:
## AIM:
To implement a simple hash generation and verification process using a custom hash function based on XOR and addition.

## ALGORITHM:

### STEP 1:
Input a message from the user.

### STEP 2:
Use a basic custom hash function that applies XOR and addition on each character of the message.

### STEP 3:
Convert the resulting hash into a hexadecimal format.

### STEP 5:
Verify the hash by comparing it with a received hash entered by the user.
## Program:
```py
# Function to compute a simple hash using XOR and addition
def compute_simple_hash(message):
    temp = 0

    # Simple hash computation: XOR and addition
    for char in message:
        temp = temp ^ ord(char)  # XOR each character
        temp += ord(char)        # Add each character's value

    # Return the result as a 1-byte hash
    return temp & 0xFF  # Ensure the hash is within a byte (0-255)

def main():
    # Step 1: Input the message
    message = input("Enter the message: ")

    # Step 2: Compute the simple hash
    hash_value = compute_simple_hash(message)

    # Step 3: Display the computed hash in hexadecimal format
    print(f"Computed Hash (in hex): {hash_value:02x}")

    # Step 5: Verify the hash
    received_hash_hex = input("Enter the received hash (in hex): ")

    # Convert received hash from hex string to an integer
    received_hash_value = int(received_hash_hex, 16)

    # Compare the computed hash with the received hash
    if hash_value == received_hash_value:
        print("Hash verification successful. Message is unchanged.")
    else:
        print("Hash verification failed. Message has been altered.")

if __name__ == "__main__":
    main()
```
## Output:

![image](https://github.com/user-attachments/assets/c39679d4-e15b-4820-986c-7cda7b5d2906)

## Result:
The program for generating and verifying a simple hash using a custom hash function was successfully implemented and executed. The computed hash ensures basic message integrity and was successfully verified against the received hash.
