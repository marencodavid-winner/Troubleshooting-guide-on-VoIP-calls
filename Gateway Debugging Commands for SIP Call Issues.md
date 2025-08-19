🔧 Gateway Debugging Commands for SIP Call Issues
This technical reference includes essential Cisco IOS commands and procedures used in the diagnosis and troubleshooting of SIP calls, voice gateway issues, analog port behavior, and SIP-UA signaling. This guide is relevant for CUCM-integrated environments as well as standalone SIP infrastructures.

🔍 Interface and Port Analysis
show interface <interface_name>
show ip interface brief
show voice port summary
show voice port
Use these commands to verify interface status (up/down), administrative status, and physical signal presence on FXS/FXO ports.
📶 Analog Port Diagnostics (FXS/FXO)
show voice call summary
debug voice ccapi inout
debug voip vtsp all
debug vpm signal
Use these to trace the signaling flow for analog ports and call control behavior. Especially useful when troubleshooting:
No dial tone

Disconnect supervision
Dead air on calls
Ring not detected on incoming FXO calls

📡 SIP Signaling & Call Processing
debug ccsip messages
debug ccsip calls
show sip-ua status
show sip-ua statistics
Use these to review SIP INVITE/100 Trying/180 Ringing/200 OK message flows. Helpful for:
One-way audio

Call setup delay

SIP trunk misconfiguration

Codec negotiation issues
⚠️ Alarms and Hardware Health
show environment all
show platform
show logging
Use to check:
Power supply or fan failures

CPU/memory usage
Unexpected system restarts
SNMP-based alerts or traps

📦 Packet Capture / Monitor Tools
On platforms that support it:
monitor capture buffer MYBUFFER size 512 max-size 1518 circular
monitor capture point ip cef MYPOINT <interface> both
monitor capture point associate MYPOINT MYBUFFER
monitor capture start
monitor capture stop
monitor capture export tftp://<server>/capture.pcap
Useful for deep packet analysis in Wireshark. Filter by SIP, RTP, or signaling anomalies.
🧠 Tips
Always synchronize logs with timestamps during testing.
Use term mon to display debug output on terminal.
Disable debugs with undebug all after testing.









