#!/bin/bash

TARGET=$1
OUTPUT_DIR="output"
REPORT="$OUTPUT_DIR/report.html"

mkdir -p $OUTPUT_DIR
> $REPORT

echo "[*] Starting scan on: $TARGET"

# Step 1: Subdomain Enumeration
echo "[*] Finding subdomains..."
subfinder -d $TARGET -silent > $OUTPUT_DIR/subs.txt

# Step 2: Check live subdomains
echo "[*] Checking live subdomains..."
httpx -l $OUTPUT_DIR/subs.txt -silent > $OUTPUT_DIR/live_subs.txt

# Step 3: Subdomain takeover check
echo "[*] Checking for subdomain takeover..."
nuclei -l $OUTPUT_DIR/live_subs.txt -t subdomain-takeover -silent -o $OUTPUT_DIR/takeover.txt

# Step 4: Check for SSRF, SQLi, XSS, NoSQLi with Nuclei
echo "[*] Running Nuclei vuln templates..."
nuclei -l $OUTPUT_DIR/live_subs.txt -t vulnerabilities/ -silent -o $OUTPUT_DIR/vulns.txt

# Step 5: Generate HTML Report
echo "[*] Generating report..."
{
  echo "<html><head><title>Scan Report for $TARGET</title></head><body><h1>Vulnerability Report for $TARGET</h1>"
  echo "<h2>Subdomain Takeover</h2><pre>$(cat $OUTPUT_DIR/takeover.txt)</pre>"
  echo "<h2>Vulnerabilities</h2><pre>$(cat $OUTPUT_DIR/vulns.txt)</pre>"
  echo "</body></html>"
} > $REPORT

echo "[+] Report saved to $REPORT"
