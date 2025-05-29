# Search Engine Recon Notes by Hexamew

## 🧠 Intro

In cybersecurity, harnessing the full power of search engines can be a great way to gather information and look for vulnerabilities in systems we are authorized to test. We do this by using search engines with their specific advanced operators.  
Below you’ll find some of the most commonly used search engines and how each one can be applied in specific contexts.

---

## 🔎 Most Useful Search Engines

### **Google**

Google is widely used for reconnaissance in ethical hacking. Using advanced search operators (like `site:`, `filetype:`, `intitle:`, `inurl:`, etc.), we can uncover sensitive information unintentionally exposed online—such as login portals, exposed documents, configuration files, camera feeds, or software version leaks.

### **Shodan**

Shodan is a search engine for Internet-connected devices and systems such as servers, routers, webcams, and IoT devices. It allows you to search by banner, port, device type, or software version.

### **Censys**

Censys focuses on Internet-connected hosts, websites, certificates, and other assets. It’s useful for enumerating domains in use, auditing open ports/services, and discovering rogue or forgotten infrastructure.

### **VirusTotal**

VirusTotal is a virus-scanning service that analyzes files and URLs with over 60 antivirus engines. It also lets you search by file hash (e.g., MD5, SHA256) to view previous scan results and community tags.

### **Have I Been Pwned**

"Have I Been Pwned" is a breach database where you can check if an email address has appeared in a known data breach. Sometimes, breached passwords may also be accessible (hashed or plain).

### **CVE.org**

CVE (Common Vulnerabilities and Exposures) is a public dictionary of known vulnerabilities. Each entry has a unique CVE ID, making it easy to reference specific security flaws across platforms and tools.

### **Exploit-DB**

Exploit Database is a collection of exploit code and proof-of-concepts for known vulnerabilities. It’s useful for researching exploitation techniques and verifying vulnerability impact.

### **GitHub**

GitHub is a software development platform, but it’s also a goldmine for security tools, PoCs, exploit scripts, and documentation. Searching for `CVE-XXXX-XXXX` can often yield working code or mitigation tips.

---

## 🔧 Common Search Operators by Platform

### 🔍 Google

| Operator             | Description                            | Example                             |
|----------------------|----------------------------------------|-------------------------------------|
| `site:`              | Limit results to a specific domain     | `site:example.com`                  |
| `filetype:`          | Search for specific file types         | `filetype:pdf confidential`         |
| `intitle:`           | Search keywords in page title          | `intitle:"index of"`                |
| `inurl:`             | Search keywords in URL                 | `inurl:admin`                       |
| `cache:`             | Show Google’s cached version of a site | `cache:example.com`                 |
| `ext:`               | Same as `filetype:`                    | `ext:sql`                           |
| `-`                  | Exclude a word                         | `admin -login`                      |
| `""`                 | Search exact phrase                    | `"confidential document"`           |
| `OR`                 | Logical OR for terms                   | `admin OR login`                    |
| `*`                  | Wildcard for any word                  | `"index of * backup"`               |
| `after:` / `before:` | Filter by indexed date                 | `site:example.com after:2022-01-01` |

---

### 🛰 Shodan

| Operator             | Description                        | Example                  |
|----------------------|------------------------------------|--------------------------|
| `hostname:`          | Filter by hostname                 | `hostname:example.com`   |
| `port:`              | Filter by open port                | `port:22`                |
| `country:`           | Filter by country                  | `country:"US"`           |
| `os:`                | Filter by operating system         | `os:"Windows 10"`        |
| `product:`           | Filter by service or software name | `product:"Apache httpd"` |
| `org:`               | Filter by organization             | `org:"Amazon"`           |
| `before:` / `after:` | Filter by last seen date           | `after:2023-01-01`       |

---

### 🌐 Censys

| Operator                      | Description                              | Example                              |
|-------------------------------|------------------------------------------|--------------------------------------|
| `services.service_name:`      | Search by service name (e.g., HTTP, SSH) | `services.service_name: "HTTP"`      |
| `services.port:`              | Filter by open port                      | `services.port:443`                  |
| `location.country:`           | Filter by country                        | `location.country: "Germany"`        |
| `services.software.product:`  | Search by product name                   | `services.software.product: "nginx"` |
| `ip:`                         | Search by specific IP                    | `ip:192.168.1.1`                      |
| `parsed.names:`               | Search for domain names                  | `parsed.names: "example.com"`        |

---

### 🧪 VirusTotal

| Field        | Description                                | Example                            |
|--------------|--------------------------------------------|------------------------------------|
| Hash Search  | Search by MD5/SHA1/SHA256                  | `44d88612fea8a8f36de82e1278abb02f` |
| `type:file`  | Show only file results                     | `type:file`                        |
| `type:url`   | Show only URL results                      | `type:url`                         |
| Tag Search   | Filter by threat tags (e.g., malware type) | `tag:"powershell"`                 |

---

> 💡 **Note:** Each platform has its own search operators and query syntax. It's always a good idea to read the official documentation of each tool to learn the full range of supported operators and their capabilities.
