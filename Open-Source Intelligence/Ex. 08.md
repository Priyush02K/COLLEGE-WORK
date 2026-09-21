# Experiment 08 — IP Address Geolocation Using OSINT Tools

## Title

**Determine the Geolocation of IP Addresses Using OSINT Tools and Databases**

---

## Aim

To use OSINT tools, online IP geolocation services, and publicly available databases to determine the **approximate geographical location** of at least 10 IP addresses, including country, region, city, ISP/organization, latitude, and longitude where available.

---

## Objectives

After completing this experiment, students will be able to:

1. Understand the concept of IP address geolocation.
2. Identify the approximate geographical location associated with an IP address.
3. Use online IP geolocation tools and databases.
4. Collect country, region, city, ISP, ASN, latitude, and longitude information.
5. Compare results from multiple IP geolocation sources.
6. Identify differences between geolocation databases.
7. Understand the limitations and accuracy of IP-based geolocation.
8. Prepare a structured IP geolocation report.

---

# 1. Theory

## What is IP Geolocation?

**IP geolocation** is the process of estimating the geographical location associated with an IP address using publicly available databases and network information.

An IP geolocation service may provide information such as:

```text
IP Address
     ↓
Country
     ↓
Region / State
     ↓
City
     ↓
ISP / Organization
     ↓
ASN
     ↓
Approximate Latitude / Longitude
```

### Example

For a sample IP:

```text
IP Address: 8.8.8.8
```

A geolocation service may return information similar to:

```text
Country: United States
Region: California
City: Mountain View
Organization: Google
```

The exact result can vary between databases.

---

# 2. Important Concept

> **IP geolocation does not normally identify the exact physical address of a person or device.**

The result generally represents the approximate location of the:

* ISP
* Network
* Data center
* Corporate network
* VPN endpoint
* Proxy
* Hosting provider

Therefore, students should record the result as **approximate geolocation**.

---

# 3. Tools Required

| Sr. No. | Tool / Database                 | Purpose                                                |
| ------: | ------------------------------- | ------------------------------------------------------ |
|       1 | **IPinfo**                      | IP location, ASN, organization and network information |
|       2 | **MaxMind GeoIP**               | IP geolocation database                                |
|       3 | **ip-api**                      | Country, region, city, ISP and coordinates             |
|       4 | **DB-IP**                       | IP geolocation and network information                 |
|       5 | **ARIN / RIPE NCC / APNIC**     | Regional Internet Registry information                 |
|       6 | **WHOIS / RDAP**                | IP allocation and organization information             |
|       7 | **Google Maps / OpenStreetMap** | Visualize approximate coordinates                      |
|       8 | **DNS Lookup**                  | Obtain IP addresses from authorized domains            |

---

# 4. IP Address Selection

Students must collect at least **10 IP addresses**.

IP addresses may be obtained from:

* Authorized websites
* Laboratory systems
* Public DNS records
* Officially provided datasets
* Public IP-geolocation datasets

### Example IP List

For demonstration, the following well-known public IPs can be used:

| Sr. No. | IP Address        | Example Purpose |
| ------: | ----------------- | --------------- |
|       1 | `8.8.8.8`         | Public DNS      |
|       2 | `1.1.1.1`         | Public DNS      |
|       3 | `9.9.9.9`         | Public DNS      |
|       4 | `208.67.222.222`  | Public DNS      |
|       5 | `8.8.4.4`         | Public DNS      |
|       6 | `1.0.0.1`         | Public DNS      |
|       7 | `149.112.112.112` | Public DNS      |
|       8 | `208.67.220.220`  | Public DNS      |
|       9 | `4.2.2.1`         | Public DNS      |
|      10 | `4.2.2.2`         | Public DNS      |

> The actual geolocation should be obtained from the tools during the experiment rather than copied from this example.

---

# 5. Method 1 — IPinfo

## Step 1

Open the IP information service.

## Step 2

Enter an IP address.

Example:

```text
8.8.8.8
```

## Step 3

Record the information returned.

Typical information may include:

```text
IP Address
Country
Region
City
Postal Code
Organization
ASN
Timezone
Coordinates
```

## Step 4

Repeat for all 10 IP addresses.

---

# 6. Method 2 — ip-api

Enter the IP address into the IP geolocation service.

Example:

```text
8.8.8.8
```

Possible fields:

| Field        | Example              |
| ------------ | -------------------- |
| Country      | United States        |
| Region       | California           |
| City         | Mountain View        |
| ISP          | Example ISP          |
| Organization | Example Organization |
| AS           | ASxxxxx              |
| Latitude     | xx.xxxx              |
| Longitude    | -xxx.xxxx            |
| Timezone     | America/Los_Angeles  |

Record the actual values returned during the experiment.

---

# 7. Method 3 — WHOIS / RDAP

IP geolocation should also be compared with **IP registration information**.

### Procedure

1. Enter the IP address into a suitable WHOIS/RDAP service.
2. Identify the Regional Internet Registry.
3. Record the allocated organization/network.
4. Compare it with the geolocation result.

### Example

| Parameter                    | Finding    |
| ---------------------------- | ---------- |
| IP                           | `8.8.8.8`  |
| Registry                     | __________ |
| Organization                 | __________ |
| Network                      | __________ |
| Country in registration data | __________ |

---

# 8. Method 4 — MaxMind GeoIP

Use a GeoIP database/service to determine the approximate location.

Record:

* Country
* Region
* City
* Postal code where available
* Latitude
* Longitude
* Accuracy information if provided

### Observation

| Parameter           | Finding    |
| ------------------- | ---------- |
| IP Address          | __________ |
| Country             | __________ |
| Region              | __________ |
| City                | __________ |
| Latitude            | __________ |
| Longitude           | __________ |
| Accuracy/Confidence | __________ |

---

# 9. Geolocation of 10 IP Addresses

This is the **main experiment table**.

| Sr. No. | IP Address      | Country | Region/State | City   | ISP/Organization | Latitude | Longitude |
| ------: | --------------- | ------- | ------------ | ------ | ---------------- | -------: | --------: |
|       1 | 8.8.8.8         | ______  | ______       | ______ | ______           |   ______ |    ______ |
|       2 | 1.1.1.1         | ______  | ______       | ______ | ______           |   ______ |    ______ |
|       3 | 9.9.9.9         | ______  | ______       | ______ | ______           |   ______ |    ______ |
|       4 | 208.67.222.222  | ______  | ______       | ______ | ______           |   ______ |    ______ |
|       5 | 8.8.4.4         | ______  | ______       | ______ | ______           |   ______ |    ______ |
|       6 | 1.0.0.1         | ______  | ______       | ______ | ______           |   ______ |    ______ |
|       7 | 149.112.112.112 | ______  | ______       | ______ | ______           |   ______ |    ______ |
|       8 | 208.67.220.220  | ______  | ______       | ______ | ______           |   ______ |    ______ |
|       9 | 4.2.2.1         | ______  | ______       | ______ | ______           |   ______ |    ______ |
|      10 | 4.2.2.2         | ______  | ______       | ______ | ______           |   ______ |    ______ |

---

# 10. Cross-Verification Using Multiple Sources

A single geolocation database should not automatically be treated as completely accurate.

Students should compare at least **two sources**.

### Example

| IP        | Tool 1 City | Tool 2 City | Match? | Final Observation |
| --------- | ----------- | ----------- | ------ | ----------------- |
| `8.8.8.8` | ______      | ______      | Yes/No | ______            |
| `1.1.1.1` | ______      | ______      | Yes/No | ______            |
| `9.9.9.9` | ______      | ______      | Yes/No | ______            |

### Why Compare?

Different databases may produce different:

```text
Country
Region
City
Coordinates
ISP
Organization
```

This occurs because different providers use different datasets and update schedules.

---

# 11. Coordinate Verification

If latitude and longitude are provided, students can visualize the approximate location on a mapping service.

Example:

```text
Latitude:  XX.XXXX
Longitude: YY.YYYY
```

Enter the coordinates into a map.

### Record

| IP     | Latitude | Longitude | Approximate Location |
| ------ | -------: | --------: | -------------------- |
| `IP-1` |   ______ |    ______ | ______               |
| `IP-2` |   ______ |    ______ | ______               |
| `IP-3` |   ______ |    ______ | ______               |

> Coordinates should be treated as approximate and should not be interpreted as an exact device or person's physical location.

---

# 12. ASN and Organization Analysis

An IP address can also be associated with an **Autonomous System Number (ASN)**.

### Example

```text
IP Address
    ↓
ASN
    ↓
Network / Organization
    ↓
Approximate Geographic Location
```

### Table

| IP Address | ASN        | Organization | Country    |
| ---------- | ---------- | ------------ | ---------- |
| __________ | __________ | __________   | __________ |
| __________ | __________ | __________   | __________ |
| __________ | __________ | __________   | __________ |

---

# 13. Final IP Geolocation Report

Students should prepare the following final table.

| No. | IP     | Country | Region | City   | ISP/Organization | ASN    |   Lat. |  Long. | Source |
| --: | ------ | ------- | ------ | ------ | ---------------- | ------ | -----: | -----: | ------ |
|   1 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |
|   2 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |
|   3 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |
|   4 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |
|   5 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |
|   6 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |
|   7 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |
|   8 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |
|   9 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |
|  10 | ______ | ______  | ______ | ______ | ______           | ______ | ______ | ______ | ______ |

---

# 14. Accuracy and Limitations

Students must include these limitations in their report.

### IP geolocation may be inaccurate because of:

1. VPN usage
2. Proxy servers
3. Cloud infrastructure
4. CDN networks
5. Mobile networks
6. Dynamic IP addresses
7. ISP address allocation
8. Data-center locations
9. Outdated databases
10. Different geolocation methodologies

### Important

An IP address can indicate the approximate location of a **network or service**, but it generally cannot be used to determine an individual's exact street address.

---

# 15. Result

The geographical information associated with at least **10 IP addresses** was collected using OSINT-based IP geolocation tools and databases. The country, region, city, ISP/organization, ASN, and approximate coordinates were recorded and cross-verified where possible.

---

# 16. Conclusion

IP geolocation is a useful OSINT technique for understanding the approximate geographic and network context of an IP address. Combining multiple geolocation databases with WHOIS/RDAP and ASN information can improve contextual understanding. However, IP geolocation results are approximate and should not be considered proof of an exact physical location.

---

# Viva Questions

### Q1. What is IP geolocation?

IP geolocation is the process of estimating the geographical location associated with an IP address.

### Q2. Can IP geolocation provide an exact physical address?

Normally, no. It generally provides an approximate location associated with the network or service.

### Q3. What information can an IP geolocation service provide?

Country, region, city, ISP, organization, ASN, timezone, latitude and longitude may be provided.

### Q4. Why can two IP geolocation tools give different results?

They may use different databases, data sources, update schedules, and geolocation methodologies.

### Q5. What is ASN?

ASN stands for **Autonomous System Number**. It identifies an autonomous network on the Internet.

### Q6. What is WHOIS/RDAP useful for?

It can provide information about the organization or network to which an IP address is allocated.

### Q7. Why are VPNs a limitation for IP geolocation?

The observed IP may belong to the VPN server rather than the user's actual network location.

### Q8. Why should multiple databases be compared?

Cross-verification helps identify inconsistencies and provides stronger contextual evidence.

### Q9. What is the difference between IP location and device location?

IP location generally represents an approximate network location, whereas device location may come from technologies such as GPS and can be much more precise.

### Q10. How many IP addresses are required in this experiment?

At least **10 IP addresses**.

---

# Expected Learning Outcome

After completing this experiment, students will be able to:

* Perform IP address geolocation using OSINT tools.
* Identify approximate country, region and city.
* Obtain ISP, organization and ASN information.
* Extract approximate latitude and longitude.
* Cross-check results using multiple databases.
* Understand the limitations of IP-based geolocation.
* Prepare an evidence-based IP geolocation report.
