# Experiment No. 1: Email Header Analysis, Email Enumeration, and Email Metadata Analysis

## Aim

The objectives of this experiment are to:

- Perform **Email Header Analysis** to extract valuable information such as:
  - Sender IP address
  - Mail servers involved
  - Email routing path
  - Authentication results (SPF, DKIM, DMARC)
- Conduct **Email Address Enumeration** to discover publicly available email addresses associated with a target domain using tools such as **Hunter.io** and **theHarvester**.
- Analyze **Email Metadata** to identify:
  - Date and time stamps
  - Email client used
  - Originating IP address (if available)
  - Mail servers
  - Approximate geographic location of the originating mail server

> **Note:** Perform this experiment only on emails and domains that you own or for which you have explicit permission.

---

# Part 1: Email Header Analysis

## Objective

Email headers contain technical information that describes how an email traveled from the sender to the recipient. Analyzing these headers helps identify the sender, mail servers, authentication mechanisms, and delivery route.

---

## Step 1: Obtain an Email Header (Gmail)

1. Open **Gmail**.
2. Open an email that you own or have permission to inspect.
3. Click the **three-dot (⋮) menu** next to the **Reply** button.
4. Select **Show Original**.
5. Copy the complete email header.

---

## Step 2: Analyze the Header Manually

Examine the following important header fields.

| Header Field | Description |
|--------------|-------------|
| **From** | Email address of the sender |
| **To** | Recipient email address |
| **Date** | Date and time the email was sent |
| **Subject** | Subject of the email |
| **Message-ID** | Globally unique identifier of the email |
| **Return-Path** | Actual return address used for delivery |
| **Received** | List of mail servers through which the email traveled |
| **Reply-To** | Address where replies will be sent (if different from From) |
| **MIME-Version** | MIME version used |
| **Content-Type** | Type of email content |
| **User-Agent** | Email client used by sender (if available) |
| **X-Mailer** | Email application used |
| **SPF** | Sender Policy Framework authentication result |
| **DKIM** | DomainKeys Identified Mail signature verification |
| **DMARC** | Domain-based Message Authentication result |

---

## Step 3: Analyze Using an Online Header Analyzer

Use an online email header analyzer to simplify interpretation.

### Recommended Tool

**MXToolbox Header Analyzer**

https://mxtoolbox.com/SuperTool.aspx

### Procedure

1. Open the website.
2. Paste the copied email header.
3. Click **Analyze Header**.

### Information Obtained

- Sender IP Address
- Mail Servers
- Email Routing Path
- SPF Status
- DKIM Verification
- DMARC Result
- Reverse DNS Lookup
- Delivery Time
- Authentication Summary

---

# Part 2: Email Address Enumeration

## Objective

Email enumeration is the process of identifying publicly available email addresses associated with a particular organization or domain.

> Perform enumeration only against domains for which you have authorization.

---

## Method 1: Hunter.io

### Step 1

Visit:

https://hunter.io

---

### Step 2

Enter the target domain.

Example:

```
example.com
```

---

### Step 3

Click **Search**.

---

### Sample Results

```
john@example.com

admin@example.com

sales@example.com

support@example.com
```

Additional information may include:

- Full name
- Department
- Confidence score
- Email pattern
- Source of discovery

---

## Method 2: theHarvester (Kali Linux)

### Step 1

Open the Terminal.

---

### Step 2

Run the following command:

```bash
theHarvester -d example.com -b all
```

### Parameters

| Parameter | Description |
|-----------|-------------|
| `-d` | Target domain |
| `-b` | Data source (search engine) |

Common data sources include:

- all
- bing
- google
- yahoo
- linkedin
- crtsh
- dnsdumpster

---

### Step 3

Wait for the scan to complete.

---

### Example Output

#### Emails Found

```
admin@example.com

info@example.com

support@example.com
```

#### Additional Information

Depending on available public data, theHarvester may also discover:

- Hosts
- Subdomains
- Public IP Addresses
- Virtual Hosts
- DNS Information

---

# Part 3: Email Metadata Analysis

## Objective

Email metadata provides technical information about an email without examining its message content.

---

## Step 1

Open the complete email header.

---

## Step 2: Examine the Date Header

Locate:

```
Date:
```

Example:

```
Date:
Tue, 10 Jun 2025
11:25:30 +0530
```

### Information Obtained

- Date sent
- Time sent
- Sender's time zone

---

## Step 3: Find the Message-ID

Locate:

```
Message-ID:
```

Example

```
Message-ID:
<abc123@mail.example.com>
```

### Purpose

- Uniquely identifies the email
- Useful during email tracking and troubleshooting

---

## Step 4: Identify the Email Client

Look for either:

```
User-Agent:
```

or

```
X-Mailer:
```

### Examples

```
X-Mailer:
Microsoft Outlook 365
```

or

```
User-Agent:
Mozilla Thunderbird
```

### Information Obtained

- Email application used
- Operating system (sometimes)
- Software version

---

## Step 5: Identify Mail Servers

Locate one or more **Received** headers.

Example

```
Received:
from smtp.example.com
by gmail.com
```

### Information Obtained

- Sending mail server
- Receiving mail server
- Delivery sequence
- Timestamp of each hop

---

## Step 6: Determine Geographic Location

If a **public IP address** is present in the header:

1. Copy the IP address.
2. Use an IP geolocation service such as:
   - https://ipinfo.io
   - https://whatismyipaddress.com
   - https://www.maxmind.com

The lookup may reveal:

- Country
- State/Region
- City (Approximate)
- ISP
- Organization
- ASN
- Latitude/Longitude (Approximate)

> **Note:** The identified location usually belongs to the mail server or ISP, not necessarily the sender's physical location.

---

# Expected Output

After completing the experiment, students should be able to identify:

- Sender email address
- Recipient email address
- Message-ID
- Return-Path
- Email authentication status (SPF, DKIM, DMARC)
- Sender IP Address
- Mail servers involved
- Complete email routing path
- Email client used
- Date and time of transmission
- Public email addresses associated with a target domain
- Public hosts and subdomains (where available)

---

# Learning Outcomes

After completing this experiment, students will be able to:

- Understand the structure of an email header.
- Interpret SMTP routing information.
- Verify email authentication using SPF, DKIM, and DMARC.
- Perform passive email enumeration using OSINT tools.
- Analyze email metadata for digital forensic investigations.
- Identify publicly exposed email addresses and associated infrastructure.
- Estimate the geographic location of mail servers using public IP information.

---

# Precautions

- Perform email analysis only on emails that you own or have permission to inspect.
- Do not use email enumeration against unauthorized domains.
- Respect privacy policies and applicable cybersecurity laws.
- Treat discovered email addresses as sensitive information.
- Use OSINT tools responsibly and ethically.

---

# Conclusion

Email header analysis provides valuable insights into the origin, authenticity, and delivery path of an email. By examining header fields, authentication records, routing information, and metadata, investigators can identify suspicious activity, verify sender legitimacy, and support digital forensic investigations. Additionally, email enumeration tools such as **Hunter.io** and **theHarvester** help identify publicly available email addresses associated with a domain, making them valuable resources during security assessments and OSINT investigations.
