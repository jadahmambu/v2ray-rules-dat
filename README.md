# GEO ASSETS

Automated generator for custom `geosite` and `geoip` dat/db files based on [Loyalsoldier](https://github.com/Loyalsoldier/v2ray-rules-dat) infrastructure with additional customized lists.

---

## 🌐 GEOSITE.DAT

The `geosite.dat` file is compiled daily using the official compiler `v2fly/domain-list-community@latest`. It contains all the original lists from Loyalsoldier, seamlessly integrated with the following custom rules that have been strictly sanitized (removing adblocker modifiers like `$important`, wildcard asterisks `*`, and exact-match pipes `|` to ensure compiler stability):

| Category / List Name | Description | Upstream Source |
| :--- | :--- | :--- |
| `geosite:antiscam` | Blocks fraudulent and scam domains. | [malikshi/antiscam](https://github.com/malikshi/antiscam) |
| `geosite:rule-ads` | Extended ad-blocking list (merged with d3ward). | [malikshi/v2ray-rules-dat](https://github.com/malikshi/v2ray-rules-dat) & [d3ward/toolz](https://github.com/d3ward/toolz) |
| `geosite:rule-malicious` | Lightweight DNSBL blocklist targeting malicious hostnames. | [elliotwutingfeng/Inversion-DNSBL-Blocklists](https://github.com/elliotwutingfeng/Inversion-DNSBL-Blocklists) |
| `geosite:bank-id` | Indonesian banking and financial services. | [malikshi/v2ray-rules-dat](https://github.com/malikshi/v2ray-rules-dat) |
| `geosite:oisd-full` | Comprehensive DNS-level ad and tracker protection. | [oisd.nl (dnsmasq format)](https://oisd.nl) |
| `geosite:oisd-nsfw` | Adult content and NSFW filtering list. | [nsfw.oisd.nl](https://oisd.nl) |
| `geosite:rule-eco` | Custom optimization and eco-mode routing lists. | Local repository (`rule_eco.txt`) |
| `geosite:rule-microsoft` | Dedicated Microsoft services and telemetry rules. | Local repository (`rule_microsoft.txt`) |
| `geosite:adguard-dns` | Aggressive DNS tracking and advertisement filter. | [AdGuardSDNSFilter](https://github.com/AdGuardTeam/AdGuardSDNSFilter) |
| `geosite:sosmed` | Social media platforms (TikTok, Meta, Instagram, X/Twitter, SnackVideo, etc.). | Local repository (`rule_sosmed.txt`) |
| `geosite:streaming` | Video and audio streaming services (YouTube, Netflix, Disney+, Spotify, etc.). | Local repository (`rule_streaming.txt`) |
| `geosite:vidconference` | Video conferencing optimization (Zoom, MS Teams, Google Meet, Webex, etc.). | Local repository (`rule_videoconference.txt`) |

---

## 🗺️ GEOIP.DAT

Generated on top of the [@Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) ecosystem. The core dataset is fetched and synced directly with daily release tags from `malikshi/geoip` to provide optimal IP routing precision.

### 📊 Data Sources & Features
* **Global IP Address Base:** Powered by **MaxMind GeoLite2** for both IPv4 and IPv6 networks.
* **China Regional Optimization (`CN`):** Mainland China networks are heavily enhanced using optimized routing tables from **ipip.net** and **@gaoyifan/china-operator-ip**.
* **Advanced Routing Categories:** Pre-built tags compiled specifically for proxy rule management, infrastructure bypassing, and privacy control:

```text
├── geoip:cloudflare       # Cloudflare CDN Nodes
├── geoip:cloudfront       # AWS CloudFront Infrastructure
├── geoip:facebook         # Meta / Facebook Network Ranges
├── geoip:fastly           # Fastly Edge Cloud Network
├── geoip:google           # Google Services & Infrastructure
├── geoip:netflix          # Netflix Streaming & Open Connect ISP IPs
├── geoip:telegram         # Telegram Messenger Datacenters
├── geoip:twitter          # X / Twitter Network Infrastructure
├── geoip:malicious        # Known Malicious & Phishing IPs
├── geoip:firewall         # Security & Restricted Firewalls
├── geoip:geoid            # Custom Geo-Identity IPs
├── geoip:doh              # DNS-over-HTTPS Server Endpoints
└── geoip:tor              # Tor Onion Network Exit Nodes
