# 🛡️ IP Blocklist - 10,000 Recent Malicious IPs

Automated daily sync of up to **10,000 recent malicious IPs** from AbuseIPDB, organized by country.

## 📊 Current Statistics

- **Total Malicious IPs**: 10,000
- **Countries Represented**: 132
- **Last Updated**: 2026-10-06T22:03:26.923Z
- **Next Update**: Automatically runs daily at midnight UTC

## 🌍 Top Countries by IP Count

| Rank | Country | Code | IP Count | List |
|------|---------|------|----------|------|
| 1 | United States | US | 2,775 | [View](./countries/us/list.txt) |
| 2 | China | CN | 1,137 | [View](./countries/cn/list.txt) |
| 3 | Netherlands | NL | 707 | [View](./countries/nl/list.txt) |
| 4 | United Kingdom | GB | 527 | [View](./countries/gb/list.txt) |
| 5 | Germany | DE | 512 | [View](./countries/de/list.txt) |
| 6 | South Korea | KR | 429 | [View](./countries/kr/list.txt) |
| 7 | HK | HK | 318 | [View](./countries/hk/list.txt) |
| 8 | SG | SG | 307 | [View](./countries/sg/list.txt) |
| 9 | India | IN | 289 | [View](./countries/in/list.txt) |
| 10 | France | FR | 233 | [View](./countries/fr/list.txt) |
| 11 | Brazil | BR | 210 | [View](./countries/br/list.txt) |
| 12 | Russia | RU | 181 | [View](./countries/ru/list.txt) |
| 13 | Vietnam | VN | 175 | [View](./countries/vn/list.txt) |
| 14 | Canada | CA | 169 | [View](./countries/ca/list.txt) |
| 15 | Indonesia | ID | 168 | [View](./countries/id/list.txt) |
| 16 | TW | TW | 135 | [View](./countries/tw/list.txt) |
| 17 | Japan | JP | 126 | [View](./countries/jp/list.txt) |
| 18 | MY | MY | 107 | [View](./countries/my/list.txt) |
| 19 | Ukraine | UA | 89 | [View](./countries/ua/list.txt) |
| 20 | Romania | RO | 73 | [View](./countries/ro/list.txt) |


*...and 112 more countries*


## 📁 Repository Structure

```
/
├── README.md              # This file - Overview and stats
├── STATISTICS.md          # Detailed statistics and analysis
├── list.txt               # Complete global list (10,000 IPs)
└── countries/             # Country-specific folders (132 countries)
    ├── us/list.txt        # United States IPs
    ├── cn/list.txt        # China IPs
    ├── ru/list.txt        # Russia IPs
    └── ...                # One list.txt per country
```

## 🚀 Quick Access

- **[📄 Global IP List](./list.txt)** - All 10,000 IPs in one file
- **[📊 Detailed Statistics](./STATISTICS.md)** - Full breakdown and analysis
- **[📂 Browse by Country](./countries/)** - Country-specific lists

## 📋 IP List Format

Each IP entry includes comprehensive information:

```
IP_ADDRESS | Country: CODE | Confidence: XX% | Reason: CATEGORY1, CATEGORY2
```

**Example:**
```
192.168.1.100 | Country: US | Confidence: 95% | Reason: SSH Brute-Force, Port Scan
```

## 🏷️ Tracked Abuse Categories

- **Network Attacks**: DDoS Attack, Port Scan, Ping of Death
- **Brute Force**: SSH/FTP/Generic Brute-Force
- **Web Attacks**: Web App Attack, SQL Injection, Hacking
- **Spam**: Email Spam, Web Spam, Blog Spam
- **Fraud**: Fraud Orders, Phishing, Spoofing
- **Bots & Proxies**: Bad Web Bot, Open Proxy, VPN IP
- **Other**: Exploited Host, IoT Targeted

##  Automation

This repository is **automatically updated daily** at midnight UTC:

1.  Validates and processes each IP address
2.  Performs geolocation lookups when needed
3.  Organizes IPs by country code
4.  Updates all lists and statistics
5.  Commits changes to GitHub

## 📈 Data Quality

- **Geolocation**: Fallback lookups for missing country data
- **Categories**: Detailed abuse category mapping
- **Freshness**: Updated daily with most recent threats

## 🛠️ Usage Examples

### Download Global List
```bash
curl -O https://raw.githubusercontent.com/blackhole-networks/IP-List/main/list.txt
```

### Download Country-Specific List
```bash
curl -O https://raw.githubusercontent.com/blackhole-networks/IP-List/main/countries/us/list.txt
```

### Use in Firewall Rules
```bash
# Example: Block IPs using iptables
while read line; do
    ip=$(echo $line | cut -d'|' -f1 | xargs)
    iptables -A INPUT -s $ip -j DROP
done < list.txt
```

## 📊 Statistics Summary

- **Valid IPs Processed**: 10,000
- **Invalid IPs Filtered**: 0
- **Fallback Lookups**: 0
- **Unknown Countries**: 0
- **Unique Countries**: 132

## ⚠️ Important Notes
- **False Positives**: Review lists before deploying to production

## 🔐 Security Considerations

- Lists are updated automatically - always use latest version
- Consider implementing whitelist for known good IPs
- Test blocking rules in non-production first
- Monitor for false positives
- Combine with other security measures

## 📞 About This Repository

This repository is maintained by an automated system that:
- Runs daily at midnight UTC
- Fetches fresh data
- Processes and validates all IPs
- Updates all files automatically
- Maintains historical accuracy

For more detailed statistics and analysis, see [STATISTICS.md](./STATISTICS.md).

---

**Automated System** | ** Daily Updates** | ** 10,000 IPs** | ** 132 Countries**

*Last Updated: 2026-10-06T22:03:26.923Z*  
*Next Update: Daily at 00:00 UTC*  
*Data Source: AbuseIPDB (Confidence 75%+)*
