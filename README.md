Sure, here is the README file with the provided code included and formatted using Markdown syntax:

---

# Caesar Cipher Text Encryption and Decryption Tool

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [Requirements](#requirements)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Code Explanation](#code-explanation)
   - [Key List](#key-list)
   - [Art](#art)
   - [Caesar Function](#caesar-function)
   - [Input Function](#input-function)
   - [Repeat Function](#repeat-function)
7. [Notes](#notes)
8. [License](#license)
9. [Contact](#contact)

## Overview
This program is a simple text-based tool for encrypting and decrypting messages using the Caesar cipher technique. The encryption and decryption process is done by shifting the letters of the message by a specified number of positions.

## Features
- **Encryption**: Secure your messages by shifting letters forward.
- **Decryption**: Restore your encrypted messages by shifting letters backward.

## Requirements
- Python 3.x

## Installation
1. Make sure you have Python 3.x installed on your machine.
2. Clone or download this repository.
3. Navigate to the directory containing the script file.

## Usage
1. Run the script:
    ```sh
    python caesar_cipher.py
    ```
2. Follow the on-screen instructions to either encrypt or decrypt a message.
3. Enter the message and the shift number when prompted.

## Code Explanation
### Key List
```python
keys = [
    'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o',
    'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', '0', '1', '2', '3',
    '4', '5', '6', '7', '8', '9', '!', '*', '[', ']', '%', '^', '=', '+', '@',
    '#', '<', '~', '`'
]
```
This list contains the characters that can be encrypted or decrypted using the Caesar cipher.

### Art
```python
art1 = ''' 
 _____                                                                             _____ 
( ___ )                                                                           ( ___ )
 |   |~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|   | 
 |   |  _____ _     _       _        ____                                          |   | 
 |   | |_   _| |__ (_)___  (_)___   / ___|__ _  ___  ___  ___ _ __                 |   | 
 |   |   | | | '_ \| / __| | / __| | |   / _` |/ _ \/ __|/ _ \ '__|                |   | 
 |   |   | | | | | | \__ \ | \__ \ | |__| (_| |  __/\__ \  __/ |                   |   | 
 |   |   |_|_|_| |_|_|___/ |_|___/  \____\__,_|\___||___/\___|_|                   |   | 
 |   |  / ___(_)_ __ | |__   ___ _ __ _ __                                         |   | 
 |   | | |   | | '_ \| '_ \ / _ \ '__| '__|                                        |   | 
 |   | | |___| | |_) | | | |  __/ |  | |                                           |   | 
 |   |  \____|_| .__/|_|_|_|\___|_|  |_|                        _   _              |   | 
 |   | | ____|_|_|    / /  _ \  ___        ___ _ __ _   _ _ __ | |_(_) ___  _ __   |   | 
 |   | |  _| | '_ \  / /| | | |/ _ \_____ / __| '__| | | | '_ \| __| |/ _ \| '_ \  |   | 
 |   | | |___| | | |/ / | |_| |  __/_____| (__| |  | |_| | |_) | |_| | (_) | | | | |   | 
 |   | |_____|_| |_/_/  |____/ \___|      \___|_|   \__, | .__/ \__|_|\___/|_| |_| |   | 
 |   | |_   _|__   ___ | |                          |___/|_|                       |   | 
 |   |   | |/ _ \ / _ \| |                                                         |   | 
 |   |   | | (_) | (_) | |                                                         |   | 
 |   |   |_|\___/ \___/|_|                                                         |   | 
 |___|~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|___| 
(_____)                                                                           (_____)
'''

art2 = '''
 _____                                                             _____ 
( ___ )                                                           ( ___ )
 |   |~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|   | 
 |   |  ____                                              _   _ _  |   | 
 |   | / ___|  ___  ___   _   _  ___  _   _   _   _ _ __ | |_(_) | |   | 
 |   | \___ \ / _ \/ _ \ | | | |/ _ \| | | | | | | | '_ \| __| | | |   | 
 |   |  ___) |  __/  __/ | |_| | (_) | |_| | | |_| | | | | |_| | | |   | 
 |   | |____/ \___|\___|  \__, |\___/ \__,_|  \__,_|_| |_|\__|_|_| |   | 
 |   |                  _ |___/   _                                |   | 
 |   |  _ __   _____  _| |_  | |_(_)_ __ ___   ___                 |   | 
 |   | | '_ \ / _ \ \/ / __| | __| | '_ ` _ \ / _ \                |   | 
 |   | | | | |  __/>  <| |_  | |_| | | | | | |  __/                |   | 
 |   | |_| |_|\___/_/\_\\__|  \__|_|_| |_| |_|\___|                |   | 
 |___|~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|___| 
(_____)                                                           (_____)

'''
```
These strings contain ASCII art for the program's output.

### Caesar Function
```python
def caesar(start_text, shift_amount, cipher_direction):
    end_text = ""
    if cipher_direction == "decode":
        shift_amount *= -1
    for letter in start_text:
        if letter in keys:
            position = keys.index(letter)
            new_position = (position + shift_amount) % len(keys)
            end_text += keys[new_position]
        else:
            end_text += letter
    print(f"\nHere's the {cipher_direction}d result: {end_text}")
```
This function performs the Caesar cipher encryption and decryption.

### Input Function
```python
def takingInputs():
    print(art1)
    direction = input("Type 'encode' to encrypt, type 'decode' to decrypt: \n")
    text = input("Type your message: \n").lower()
    shift = int(input("Type the shift number: \n"))
    caesar(start_text=text, shift_amount=shift, cipher_direction=direction)
```
This function takes user input for the direction, message, and shift number.

### Repeat Function
```python
def askAgain():
    while True:
        takingInputs()
        ask = input(
            "\nDo you want to encrypt or decrypt your messages again? ['yes' or 'no']: "
        ).lower()
        if ask == 'no':
            print(art2)
            break
        elif ask != 'yes':
            print(
                "\nYou have input an invalid option. Please enter 'yes' or 'no'."
            )

askAgain()
```
This function repeatedly asks the user if they want to encrypt or decrypt another message.

## Notes
- Ensure you provide a valid shift number and direction for accurate results.
- The shift number should be a positive integer.
- The program continues to ask for inputs until the user chooses to stop.

## License
This project is licensed under the MIT License.

## Contact
For any questions or issues, please contact [Your Name] at [Your Email].

---

Ensure the code is enclosed in triple backticks (\```) to format it correctly in the README file.
