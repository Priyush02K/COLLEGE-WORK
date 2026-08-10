# Part B — theHarvester Installation and Usage

## 10. What is theHarvester?

**theHarvester** is an OSINT reconnaissance tool used to collect publicly available information associated with a domain.

Depending on the installed version and configured sources, it may identify:

- Email addresses
- Hosts
- Subdomains
- IP addresses
- URLs
- Publicly indexed names
- PGP-related information
- Other publicly available technical information

The exact results depend on the target, source availability, tool version, and API/source configuration.

---

## 11. Lab Requirements

### Software

- Kali Linux
- Internet connection
- theHarvester
- Web browser

### Target

Use only:

```text
YOUR-AUTHORIZED-DOMAIN
```

For example, an instructor-provided lab domain.

> **Do not investigate or actively scan an organization without authorization.**

---

## 12. Check Kali Linux

Open Terminal.

Check operating-system information:

```bash
uname -a
```

or:

```bash
cat /etc/os-release
```

Update package information:

```bash
sudo apt update
```

---

## 13. Install theHarvester

On Kali Linux:

```bash
sudo apt install theharvester
```

Verify the installation:

```bash
theHarvester -h
```

You can also locate the executable:

```bash
which theHarvester
```

---

## 14. Understand the Basic Command

The general command structure is:

```bash
theHarvester -d <domain> -b <source>
```

Where:

- `-d` specifies the target domain.
- `-b` specifies the data source.

First inspect the available options and sources on your installed version:

```bash
theHarvester -h
```

> **Note:** Available data-source names and options can change between theHarvester versions. Always use the help output from the installed version rather than relying on an old tutorial.

---

# Part C — Collecting Public Information

## 15. Email Address Enumeration

Run theHarvester against an **authorized educational domain** using a supported public source:

```bash
theHarvester -d <AUTHORIZED-DOMAIN> -b <SOURCE>
```

Possible output may contain:

```text
Emails found:
----------------
info@example.edu
support@example.edu
admin@example.edu
```

Record the results.

### Observation Table — Email Addresses

| S.No. | Email Address | Public Source | Independently Verified? |
|---:|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

### Important

A discovered email address does **not automatically prove that the mailbox currently exists**.

---

# 16. Collect Subdomains and Hosts

Possible results may include:

```text
www.example.edu
mail.example.edu
portal.example.edu
```

Record:

| S.No. | Host/Subdomain | IP Address (if reported) | Source |
|---:|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

### Understanding the Relationship

```text
example.edu
     |
     +-- www.example.edu
     |
     +-- mail.example.edu
     |
     +-- portal.example.edu
```

A subdomain is part of the organization's domain namespace and may identify a particular service or application.

---

# 17. Verify DNS Information

For an authorized domain/host, DNS information can be checked using:

```bash
nslookup <AUTHORIZED-HOST>
```

or:

```bash
dig <AUTHORIZED-HOST>
```

Example:

```bash
nslookup mail.example.edu
```

This demonstrates:

```text
Hostname
   |
   v
DNS Resolution
   |
   v
IP Address
```

---

# 18. Identify Publicly Indexed Names

Depending on the source, theHarvester may return publicly indexed names associated with the organization.

Example:

```text
John Smith
Priya Sharma
Rahul Patel
```

Record only information that is publicly available and relevant to the investigation.

| S.No. | Name | Associated Public Source | Verified? |
|---:|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

### Important

A returned name should **not automatically be considered an employee**. Verify it through an appropriate public source, such as an official organizational page or a public professional profile.

---

# 19. PGP Information

Public PGP key sources may contain information such as:

- Public keys
- Names
- Email addresses

This can help correlate a publicly available email address with an identity.

Record:

| S.No. | PGP/Key Information | Associated Email/Name | Source |
|---:|---|---|---|
| 1 | | | |
| 2 | | | |

---

# Part D — Open Ports and Service Information

## 20. Important Distinction

TheHarvester is primarily a **passive OSINT information-gathering tool**.

If a public source reports a port or service, that is different from directly scanning a target.

### Passive

```text
Public Source
     |
     v
Previously indexed information
     |
     v
Port/Service information
```

### Active

```text
Your Computer
     |
     v
Direct connection to target
     |
     v
Port Scan
     |
     v
Port/Service information
```

Active scanning must only be performed against an **authorized lab machine or system**.

---

## 21. Authorized Port Enumeration

If the instructor provides a lab machine for scanning, use:

```bash
nmap <AUTHORIZED-LAB-IP>
```

Example result:

```text
PORT     STATE    SERVICE
22/tcp   open     ssh
80/tcp   open     http
443/tcp  open     https
```

Record:

| S.No. | Port | State | Service |
|---:|---:|---|---|
| 1 | 22/tcp | open | ssh |
| 2 | 80/tcp | open | http |
| 3 | 443/tcp | open | https |

---

# 22. Service and Banner Identification

Against an **authorized lab host**, service/version identification can be performed using:

```bash
nmap -sV <AUTHORIZED-LAB-IP>
```

Example:

```text
PORT     STATE    SERVICE  VERSION
22/tcp   open     ssh      OpenSSH ...
80/tcp   open     http     Apache ...
```

The version information is useful for understanding the technical footprint.

Record:

| S.No. | Port | Service | Version/Banner |
|---:|---:|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

# Part E — Save theHarvester Results

Save terminal output for your lab report:

```bash
theHarvester -d <AUTHORIZED-DOMAIN> -b <SOURCE> | tee harvester_results.txt
```

This creates:

```text
harvester_results.txt
```

Students can use this file as supporting evidence for their observations.

---

# 23. Complete Information-Gathering Workflow

```text
                 Authorized Domain
                        |
                        v
                  theHarvester
                        |
        +---------------+---------------+
        |               |               |
        v               v               v
     Emails          Hosts         Subdomains
        |               |               |
        +---------------+---------------+
                        |
                        v
                 IP Information
                        |
                        v
              Public Verification
                        |
                        v
            Authorized Lab Host?
                  /          \
                NO            YES
                |              |
                v              v
              Stop           Nmap
                               |
                       +-------+-------+
                       |               |
                       v               v
                     Ports         Services
                                       |
                                       v
                                    Banners
```

---

# 24. Final Observation Table

| S.No. | Information Type | Observation |
|---:|---|---|
| 1 | Target Domain | |
| 2 | Email Addresses | |
| 3 | Subdomains | |
| 4 | Hosts | |
| 5 | IP Addresses | |
| 6 | Publicly Indexed Names | |
| 7 | URLs | |
| 8 | PGP Information | |
| 9 | Publicly Reported Ports | |
| 10 | Services/Banners | |

---

# 25. Analysis

Students should analyze the collected information rather than simply copying tool output.

Answer the following:

1. How many email addresses were discovered?
2. How many subdomains were identified?
3. Which hosts were discovered?
4. Which IP addresses were reported?
5. Were any publicly indexed names identified?
6. Which public sources produced the information?
7. Was PGP-related information available?
8. Were any ports publicly reported?
9. Which services were associated with the ports?
10. Which findings were independently verified?
11. Which findings could not be verified?
12. Which activities were passive?
13. Which activities were active?
14. Why is authorization important before performing active reconnaissance?

---

# 26. Result

The student successfully performed **email header analysis** and used **theHarvester** to collect and analyze publicly available information associated with an authorized domain. The student also understood the distinction between passive OSINT collection and authorized active technical reconnaissance.

---

# 27. Precautions and Ethical Guidelines

1. Use only authorized domains and systems.
2. Do not attempt to access private email accounts.
3. Do not guess passwords or attempt account access.
4. Do not send phishing emails as part of this experiment.
5. Do not perform port scanning against unauthorized systems.
6. Do not exploit discovered vulnerabilities.
7. Do not collect unnecessary personal information.
8. Verify important findings using multiple reliable sources.
9. Protect any sensitive data collected during the practical.
10. Follow institutional policies and applicable laws.

---

# 28. Viva Questions

1. What is OSINT?
2. What is theHarvester?
3. Is theHarvester primarily passive or active?
4. What information can theHarvester collect?
5. What is an email header?
6. What is the purpose of the `Received` header?
7. What is a Message-ID?
8. What is SPF?
9. What is DKIM?
10. What is DMARC?
11. Is the sender's IP address always visible in an email header?
12. What is a subdomain?
13. What is a hostname?
14. What is DNS?
15. Why should OSINT results be verified?
16. What is the difference between passive and active information gathering?
17. Why does port scanning require authorization?
18. What is service/banner identification?
19. Why should a discovered employee name not automatically be treated as verified?
20. What is the difference between raw data and intelligence?

---

# 29. Key Learning Point

```text
Collection
    |
    v
Verification
    |
    v
Correlation
    |
    v
Analysis
    |
    v
Intelligence
```

> **OSINT is not simply finding information. The real skill is determining whether the information is relevant, accurate, reliable, and meaningful.**
