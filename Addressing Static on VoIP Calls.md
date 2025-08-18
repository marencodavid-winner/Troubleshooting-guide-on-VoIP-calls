# Addressing Static on VoIP Calls

Static or audio degradation on VoIP calls can result from a range of issues: network instability, faulty hardware, misconfigurations, or environmental interference. This troubleshooting guide applies universally, regardless of platform (Cisco CUCM, FreePBX, Genesys, etc.).

---
## 🔧 Common Causes

### Network Issues
- **Latency & Jitter**: High levels result in distorted or choppy audio.
- **Packet Loss**: Lost voice packets degrade quality and introduce static.
- **Bandwidth Congestion**: Saturated networks impact VoIP performance.

### Hardware Issues
- **Headsets/Microphones**: Faulty or loose connections cause interference.
- **Network Cables**: Damaged or low-quality cables impact data transmission.

### Configuration Issues
- **Codec Mismatch**: Incompatible codecs between endpoints degrade audio.
- **QoS Misconfiguration**: VoIP traffic must be properly prioritized.
- **DSP Resource Overload**: Gateways may lack available processing power.

### Environmental Factors
- **Electromagnetic Interference (EMI)**: From microwaves, cordless phones, etc.
- **Power Supply Instability**: Fluctuating power affects network equipment.

---

## 🧭 Step-by-Step Troubleshooting

### Step 1: Network Diagnostics
- Run `ping` and `traceroute` to identify latency/jitter.
- Use **Wireshark** for deep packet inspection and VoIP traffic analysis.
- Ensure **QoS** is properly configured and consistent across all devices.

### Step 2: Hardware Inspection
- Swap out headsets and check microphone ports.
- Inspect and replace network cables if necessary.

### Step 3: System Configuration
- Verify codec settings on both endpoints (e.g., Cisco CUCM: *Device > Phone*).
- Check DSP resource usage with: show dspfarm all
- On Cisco phones, access:Settings > Status > Call Statistics
to verify packet loss, jitter, and latency.
### Step 4: Environmental Checks
- Ensure VoIP hardware is isolated from EMI sources.
- Use UPS devices to maintain power consistency.
---
## 🧪 Additional Techniques
- **CDRs (Call Detail Records)**:
- Get extension and username.
- Review CDRs for jitter, packet loss, and latency.
- Share screenshots with users if needed.
- **Testing Phones / Jabber Setup**:
- Have a test device to replicate issues.
- Route test calls through the same path and media IP.
- **Routing & Gateway Analysis**:
- Determine the media path (CUBE/VG/IP).
- Identify whether affected calls share a common route or IP.
---
## ✅ Final Advice
Troubleshooting static involves eliminating variables layer by layer: network, hardware, software, and environment. Use a combination of CLI tools, CDR analysis, Wireshark captures, and structured observation.
If the issue persists despite this guide, escalate with vendor support.
---
*Universal VoIP Diagnostic Reference* 
