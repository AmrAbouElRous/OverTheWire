Leviathan Level 0
🧠 Goal

Find the password to leviathan1 by exploring the system.

🔐 Credentials

Username: leviathan0

Host: leviathan.labs.overthewire.org

Port: 2223 (SSH)

Password: leviathan0

🖥️ Commands Used
ssh leviathan0@leviathan.labs.overthewire.org -p 2223
ls -la
cat .bash_history
strings <filename>
./<binary>

💡 Theory

SSH login is required (different from Natas which is web-based).

Check hidden files (ls -la).

Sometimes .bash_history or small binaries reveal hints.

Use strings or ltrace to analyze executables.

Goal is to find the next level’s password stored in a hidden file or revealed by a binary.

📤 Output
<password for leviathan1>
