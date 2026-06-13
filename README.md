# 🛡️ IP Blocklist - 10,000 Recent Malicious IPs

Automated daily sync of up to **10,000 recent malicious IPs** from AbuseIPDB, organized by country.

## 📊 Current Statistics

- **Total Malicious IPs**: 10,000
- **Countries Represented**: 134
- **Last Updated**: 2026-06-13T22:04:39.954Z
- **Next Update**: Automatically runs daily at midnight UTC
- **Confidence Threshold**: 75%+
- **Data Source**: AbuseIPDB API

## 🌍 Top Countries by IP Count

| Rank | Country | Code | IP Count | List |
|------|---------|------|----------|------|
| 1 | United States | US | 3,120 | [View](./countries/us/list.txt) |
| 2 | China | CN | 865 | [View](./countries/cn/list.txt) |
| 3 | United Kingdom | GB | 707 | [View](./countries/gb/list.txt) |
| 4 | Germany | DE | 695 | [View](./countries/de/list.txt) |
| 5 | Netherlands | NL | 634 | [View](./countries/nl/list.txt) |
| 6 | SG | SG | 385 | [View](./countries/sg/list.txt) |
| 7 | India | IN | 360 | [View](./countries/in/list.txt) |
| 8 | France | FR | 338 | [View](./countries/fr/list.txt) |
| 9 | HK | HK | 268 | [View](./countries/hk/list.txt) |
| 10 | South Korea | KR | 257 | [View](./countries/kr/list.txt) |
| 11 | Brazil | BR | 220 | [View](./countries/br/list.txt) |
| 12 | Japan | JP | 198 | [View](./countries/jp/list.txt) |
| 13 | Russia | RU | 153 | [View](./countries/ru/list.txt) |
| 14 | Indonesia | ID | 142 | [View](./countries/id/list.txt) |
| 15 | Canada | CA | 127 | [View](./countries/ca/list.txt) |
| 16 | MY | MY | 119 | [View](./countries/my/list.txt) |
| 17 | Vietnam | VN | 112 | [View](./countries/vn/list.txt) |
| 18 | Thailand | TH | 78 | [View](./countries/th/list.txt) |
| 19 | BG | BG | 72 | [View](./countries/bg/list.txt) |
| 20 | TW | TW | 65 | [View](./countries/tw/list.txt) |


*...and 114 more countries*


## 📁 Repository Structure

```
/
├── README.md              # This file - Overview and stats
├── STATISTICS.md          # Detailed statistics and analysis
├── list.txt               # Complete global list (10,000 IPs)
└── countries/             # Country-specific folders (134 countries)
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

## 🔄 Automation

This repository is **automatically updated daily** at midnight UTC:

1. ✅ Fetches up to 10,000 most recent malicious IPs from AbuseIPDB
2. ✅ Validates and processes each IP address
3. ✅ Performs geolocation lookups when needed
4. ✅ Organizes IPs by country code
5. ✅ Updates all lists and statistics
6. ✅ Commits changes to GitHub

## 📈 Data Quality

- **Confidence Score**: Only IPs with 75%+ confidence
- **Validation**: All IPs validated for proper format
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
- **Unique Countries**: 134

## ⚠️ Important Notes

- **Maximum Limit**: AbuseIPDB API allows maximum 10,000 IPs per request
- **False Positives**: Review lists before deploying to production
- **Rate Limiting**: Respects API rate limits during processing
- **Data Source**: All data from AbuseIPDB community reports

## 🔐 Security Considerations

- Lists are updated automatically - always use latest version
- Consider implementing whitelist for known good IPs
- Test blocking rules in non-production first
- Monitor for false positives
- Combine with other security measures

## 📞 About This Repository

This repository is maintained by an automated system that:
- Runs daily at midnight UTC
- Fetches fresh data from AbuseIPDB
- Processes and validates all IPs
- Updates all files automatically
- Maintains historical accuracy

For more detailed statistics and analysis, see [STATISTICS.md](./STATISTICS.md).

---

**🤖 Automated System** | **📅 Daily Updates** | **🛡️ 10,000 IPs** | **🌍 134 Countries**

*Last Updated: 2026-06-13T22:04:39.954Z*  
*Next Update: Daily at 00:00 UTC*  
*Data Source: AbuseIPDB (Confidence 75%+)*
