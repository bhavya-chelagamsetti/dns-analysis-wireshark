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

![Start Capture Filter](screenshots/start_capture_filter.png)<img width="774" alt="start_capture_filter" src="https://github.com/user-attachments/assets/339e4d90-9697-4fcd-9c0c-b70e8843a02a" />

---

### 2. DNS Query for reddit.com
Captured a standard DNS query for the domain `www.reddit.com`.

![DNS Query](screenshots/dns_query_redd<img width="946" alt="dns_query_reddit" src="https://github.com/user-attachments/assets/258de999-a004-43f0-8ad7-34be1b01979b" />
it.png)

---

### 3. DNS Response with CNAME
The response includes a CNAME record, redirecting the query to `www.redditstatic.com` and then to a CDN domain.

![DNS Response with CNAME](screensh<img width="739" alt="dns_response_with_cname_redditstatic" src="https://github.com/user-attachments/assets/7b9746d3-c0a0-4ab2-b342-d7f16397bd8c" />
ots/dns_response_with_cname_redditstatic.png)

---

### 4. DNS Response with Final IP
Final resolved A record showing the IP address `151.101.xx.140`, revealing CDN involvement (Fastly).

![DNS Response with IP](screensho<img width="739" alt="dns_response_with_ip" src="https://github.com/user-attachments/assets/62a704c3-4ba3-4804-bdfd-d55fa21fa9f4" />
ts/dns_response_with_ip.png)

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
