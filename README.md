# bfd-qmail-rule
A rule for BFD (Brute Force Detection) Script for qmail
https://www.rfxn.com/projects/brute-force-detection/

Add this qmail rule to your rules folder (typically /usr/local/bfd/rules)

```
PORTS="25"
LP="/var/log/smtp/current"
TLOG_TF="qmail-smtpd"
TMP="/usr/local/bfd/tmp"

## qmail-smtpd AUTH Failures
ARG_VAL=`$TLOG_PATH $LP $TLOG_TF | grep "AUTH failed" | sed -n 's/.*AUTH failed \[\([0-9]\+\.[0-9]\+\.[0-9]\+\.[0-9]\+\)\] \([^ ]*\).*/\1:\2/p'`
```
