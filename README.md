# SHA256 Password Cracker

## Objective  
Brute-force a given SHA256 hash using a wordlist (`rockyou.txt`) and Python scripting to simulate password cracking logic used in real-world attacks.

## Skills Learned

- **Python Scripting**: Developed a custom hash brute-force tool using Python and the `pwntools` library.
- **Password Cracking Logic**: Implemented iterative SHA256 hash comparisons against a known password list.
- **Wordlist Processing**: Efficiently parsed and encoded large password lists, including special character handling (`latin-1` encoding).
- **Hashing Algorithms**: Applied SHA256 hashing to input data and validated against target hashes.
- **Command-Line Tool Design**: Built and tested a CLI tool with argument validation and user feedback using `sys.argv` and `pwntools.log`.

## Tools Used  
- **Python** 
- **pwntools**
- **Linux Terminal**

## Steps

1. **Set Up Environment**  
   - Install Python and `pwntools`:  
     ```bash
     pip install pwntools
     ```

2. **Prepare the Wordlist**  
   - Ensure `rockyou.txt` is available in your working directory.  
   - (Optional) Decompress it from Kali Linux default path:  
     ```bash
     gunzip /usr/share/wordlists/rockyou.txt.gz
     ```

3. **Run the Script**  
   - Usage:  
     ```bash
     python3 sha256_cracker.py <sha256_hash>
     ```

4. **Script Logic**  
   - Takes the target SHA256 hash from the command line.
   - Reads and encodes each password from `rockyou.txt` using `latin-1`.
   - Hashes the password with SHA256 and compares it to the target.
   - Stops on a successful match or exits with failure if not found.

<img width="1550" height="620" alt="image" src="https://github.com/user-attachments/assets/d9f92f96-dcfc-4dad-bd92-05dd4eec9675" />

Tested the script by getting the sha256 sum of the plaintext python:

<img width="783" height="104" alt="image" src="https://github.com/user-attachments/assets/1dd610e6-7c5c-4fee-aa6c-c3d73c371ee3" />
<img width="973" height="103" alt="image" src="https://github.com/user-attachments/assets/b838d851-cce1-47f8-994b-ff13c901d0d5" />

Result:

Uses log.progress to iterate each line in the rockyou.txt file, with each line cleaning up the string and calculating the sha256 hash sum of htat string and comparing it with the unknown input. When the hash is matched, the input is then printed to the screen.

<img width="988" height="277" alt="image" src="https://github.com/user-attachments/assets/90a5dc7f-6429-4446-a50f-27ff26c0c055" />
