# Linux Commands Notes

A collection of commonly used Linux commands with explanations and examples.

---

## 1. File & Directory Navigation
- **pwd** → Shows the present working directory path.  
- **cd `<directory>`** → Change directory (move into directories).  
- **man `<command>`** → Shows the manual (documentation) of a command.  

---

## 2. File Viewing & Creation (cat command)
- **cat `<filename>`** → Concatenate and display file contents.  
- **cat -n `<filename>`** → Number all lines in a file.  
- **cat -b `<filename>`** → Number only non-blank lines.  
- **cat -s `<filename>`** → Remove multiple blank lines (squeeze).  
- **cat -E `<filename>`** → Show `$` at the end of each line.  
- **cat > `<filename>`** → Create a file and write content (press `Ctrl+D` to save).  
- **cat >> `<filename>`** → Append content to an existing file.  

---

## 3. File Operations
- **cp `<filename>` `<destination>`** → Copy a file.  
- **mv `<filename>` `<destination>`** → Move or rename a file.  
- **rm `<filename>`** → Delete a file.  
- **rm -r `<directory>`** → Remove a directory recursively.  

---

## 4. Searching & Sorting
- **grep `<word>` `<filename>`** → Search for a word in a file.  
- **sort `<filename>`** → Sort file contents alphabetically.  
  - `sort -r` → Sort in reverse order.  
  - `sort -n` → Sort numerically.  

---

## 5. File Ownership & Permissions
- **chown `<new-owner>` `<filename>`** → Change file owner.  

### Permission Values:
- `0 = --- (no permission)`  
- `1 = --x (execute)`  
- `2 = -w- (write)`  
- `4 = r-- (read)`  

Examples:
- `rwx = 4+2+1 = 7`  
- `rw- = 6`  
- `r-- = 4`  
- `r-x = 5`  

Full permission (user/group/others):  
- **777 = rwxrwxrwx**

- **chmod `<permission-number>` `<filename>`** → Change file permission.  

---

## 6. Process & File Handling
- **lsof** → List open files (everything in Linux is a file).  
  - `sudo lsof -i :8080` → Find process using port 8080.  
  - `lsof -i` → Show all network connections.  
- **id** → Show user ID and group ID.  

---

## 7. Archiving & Compression
- **tar -cvf `<archive.tar>` `<source-folder>`** → Create a tar archive.  
- **tar -xvf `<archive.tar>`** → Extract tar archive.  

---

## 8. Text Processing
- **cut -c[from]-[to] `<filename>`** → Show specific columns of text.  
- **sed 's/old/new/' `<filename>`** → Replace text in file.  
- **uniq `<filename>`** → Remove duplicate lines.  
- **awk '/pattern/ {print}' `<filename>`** → Print lines matching a pattern.  
- **tr "[a-z]" "[A-Z]"** → Convert lowercase to uppercase.  

---

## 9. Monitoring & Automation
- **watch `<command>`** → Run a command repeatedly (default every 2s).  
  - `watch -n 5 ls` → Run `ls` every 5 seconds.  
  - `watch -d <command>` → Highlight changes in output.  
- **eval "command"** → Evaluate and run a command from a string.  
- **history** → Show command history.  

---

## 10. Disk & Memory Management
- **dd if=<input> of=<output>** → Copy data at block level.  
  - Example: `dd if=/dev/hda of=/dev/hdb` (clone disk).  
- **free -m / -g** → Show memory usage in MB/GB.  
- **df -h** → Show disk free space in human-readable format.  
- **du -h -d 1 /var/** → Show disk usage for `/var` with depth 1.  

---

## 11. Networking
- **ssh `<user>@<host>`** → Securely connect to remote machine.  
  - `ssh-keygen -t rsa` → Generate SSH key pair.  
- **ip `<object>` `<command>`** → Manage network settings.  
  - `ip addr show` → Show IP addresses.  
  - `ip link show` → Show interfaces.  
  - `ip route show` → Show routing table.  
- **ifconfig** → Configure network interfaces (*deprecated*, use `ip`).  
- **netstat -a / -at** → Show network connections and ports.  
- **nslookup `<domain>`** → Query DNS for IP/domain.  
  - `nslookup google.com` → Get IP of google.com.  
  - `nslookup 8.8.8.8` → Reverse lookup domain.  
- **curl `<url>`** → Transfer data from/to server.  
  - `curl https://google.com` → Get page source.  
  - `curl -o page.html URL` → Save output to file.  

---

## 12. System & Environment
- **env** → Show environment variables or run command with custom environment.  
  - `env -i bash` → Start new shell with no environment variables.  
- **iptables** → Firewall management (example: `service iptables stop`).  
- **apt / apt-get** → Package manager for Debian-based systems.  
  - `sudo apt install git` → Install git.  

---

## 13. Shell & Scripting
- **Shell** → A command-line interpreter to interact with the OS kernel.  
- **Shell Scripting** → Writing multiple commands in `.sh` file to automate tasks.  
- **Bash (Bourne Again Shell)** → Most common Linux shell.  
  - Run script: `bash file.sh`  

---

