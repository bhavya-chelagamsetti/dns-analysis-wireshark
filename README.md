# DNS Analysis Using Wireshark

This beginner-friendly project demonstrates how to capture and analyze DNS traffic using Wireshark. The goal is to observe how domain names are resolved to IP addresses, including how CNAME records redirect queries.

---

## 📌 Objective

- Capture real-time DNS traffic
- Analyze standard queries and responses
- Identify CNAME chains and final IP resolutions
- Understand how DNS reveals CDN usage like Fastly or Cloudflare

---

## 🛠️ Tools Used

- **Wireshark** – Network protocol analyzer  
- **Public DNS Queries** – To domains like `reddit.com`  
- **Filters:** `udp.port == 53` or `dns`

---

## 📸 Screenshots

### 1. Start Capture Filter
Shows the Wireshark interface with `udp.port == 53` filter applied to capture only DNS traffic.

<img width="774" alt="start_capture_filter" src="https://github.com/user-attachments/assets/7e7c7dbe-3a2f-4bd4-9bce-2a0b1ee10e79" />


---

### 2. DNS Query for reddit.com
Captured a standard DNS query for the domain `www.reddit.com`.

![dns_query_reddit](https://github.com/user-attachments/assets/d4af6a5c-6856-48c5-8ea4-42d036b1ad81)


---

### 3. DNS Response with CNAME
The response includes a CNAME record, redirecting the query to `www.redditstatic.com` and then to a CDN domain.

<img width="739" alt="dns_response_with_cname_redditstatic" src="https://github.com/user-attachments/assets/44543ded-0bf3-4105-ab89-8202f142bb73" />


---

### 4. DNS Response with Final IP
Final resolved A record showing the IP address `151.101.xx.140`, revealing CDN involvement (Fastly).

<img width="739" alt="dns_response_with_ip" src="https://github.com/user-attachments/assets/2acc7464-09eb-4367-b936-1593a9cbdcaa" />


---

## 🔍 Key Observations

- A DNS query to `www.reddit.com` first returns a **CNAME** to `www.redditstatic.com`.
- Further redirection reveals Fastly CDN usage via `dualstack.reddit.map.fastly.net`.
- The final **A record** resolves to a **public IP** like `151.101.113.140`.

---

## 🛡️ Safety & Privacy

All captured traffic involves **public DNS data** only. No private IPs, MAC addresses, hostnames, or credentials are included in this project.

---

## 📚 What I Learned

- How to apply Wireshark display filters effectively
- How DNS queries are structured and resolved
- How CNAME chains can indicate CDN involvement
- How to extract meaningful insights from packet-level analysis

---

> **Author:** [Chelagamsetti Bhavya](https://github.com/bhavya-chelagamsetti)  
> For educational and portfolio purposes.
