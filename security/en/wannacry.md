# Info

## Best practices

 * best pratices (readable for end-users) : http://www.globallearningsystems.com/blog/post/10-best-practices-to-avoid-email-phishing-attacks/
 * lot of (very technical) best practices (from US-CERT) : https://www.us-cert.gov/ncas/tips


## Info abour Wannacry:

 * US-CERT : https://www.us-cert.gov/ncas/alerts/TA17-132A
 * `apt-get install yara` (debian8, yara = v3.1; yara latest = v3.5)
 * write the yara rules into a wannacry.yar file
 * run yara with: `yara wannacry.yar files_or_directory`


## Info about Jaff:

 * https://thehackernews.com/2017/05/decrypt-jaff-ransomware-files.html
 * https://www.tripwire.com/state-of-security/latest-security-news/jaff-virus-file-ransomware-new-locky/
 * http://www.cert.ssi.gouv.fr/site/CERTFR-2017-ALE-011/index.html


## Scan/Detection with yara

 * yara : https://github.com/VirusTotal/yara/
 * write the yara rules ([found from the US-CERT TA17-132A](https://www.us-cert.gov/ncas/alerts/TA17-132A) into a `wannacry.yar` file
 * install yara: `apt-get install yara` (debian8, yara = v3.1; yara latest = v3.5)
 * run yara with: `yara wannacry.yar files_or_directory`



# Detection

## On File-system: Scan and detection with clamav

 * clamav since 0.99.1 (0.99rc2 ?) support yara rules.
 * use the `wannacry.yar` file with clamav #TODO: not tested

## On network: Scan SMB to detect vulnerable target

 * https://gist.github.com/Neo23x0/60268852ff3a5776ef66bc15d50a024a
 *  ( http://seclists.org/nmap-dev/2017/q2/79 )
 * W: need nmap 7.x w/ lua 5.3



## On-the-fly protection for email

 * clamav with libmilter

## On-the-fly detection for web (over proxy)

 * squid >= 3.5 + (icap) yara (python): https://github.com/RamadhanAmizudin/python-icap-yara
 * (icap) yara (C) : https://github.com/fygrave/c_icap_yara

## On-the-fly protection for File-system

 * clamd + fanotify should allow to protect at the write access
 * `apt-get install clamav clamav-daemon`
 * edit config /etc/clamav/clamd.conf to enable ScanOnAccess ....
 * orignal source: https://wiki.archlinux.org/index.php/ClamAV#OnAccessScan

```
/etc/clamav/clamd.conf

# Enable son-access scan, required clamd service running
ScanOnAccess true

# Set the mount point where to recursively perform the scan,
# this could be every path or multiple path (one line for path)
OnAccessMountPath /usr
OnAccessMountPath /home/
OnAccessExcludePath /var/log/

# flag fanotify to block any events on monitored files to perform the scan
OnAccessPrevention false

# perform scans on newly created, moved, or renamed files
OnAccessExtraScanning true

# check the UID from the event of fanotify
OnAccessExcludeUID 0

# action to perform when clamav detects a malicious file
# it is possibile to specify ad inline command too
VirusEvent /etc/clamav/detected.zsh

# WARNING: clamd should run as root
User root
```
 * manual force to scan something with `clamdscan ...` (read with attention it is not `clamscan`)


## (misc) Antivirus based on clamav + fanotify
 * https://fosdem.org/2017/schedule/event/armadito/



## update de microsoft

* kb4012598 (a consulter depuis un IE ...): http://www.catalog.update.microsoft.com/Search.aspx?q=kb4012598


