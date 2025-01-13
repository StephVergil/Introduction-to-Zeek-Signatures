# Introduction to Zeek Signatures

This project delves into Zeek's signature framework, demonstrating how to create and utilize pattern-based filters for efficient network traffic analysis. By working with and modifying signature files, the lab emphasizes the practical application of Zeek in identifying and logging specific network traffic patterns, ultimately enhancing the understanding of network events.

---

## Objectives
- Configure and start Zeek for signature-based network traffic analysis.
- Execute premade Zeek signature files to identify HTTP traffic patterns.
- Modify Zeek signature files to capture specific UDP-based SNMP and DNS messages.
- Analyze logs to interpret matched signatures, triggered events, and packet payloads.

---

## Tools Used
- **Zeek**: A powerful network security monitoring tool for signature-based analysis.
- **Sample PCAP Files**: Test datasets for validating signature matching.
- **Gedit**: Text editor for viewing and editing signature files and logs.

---

## Key Steps

### **1. Starting Zeek**
- Initialize Zeek to monitor and analyze network traffic using:
  ```bash
  cd $ZEEK_INSTALL/bin && sudo ./zeekctl start
  ```

### **2. Executing Premade Zeek Signatures**
- Navigate to the **Lab-Scripts** directory:
  ```bash
  cd ~/Zeek-Labs/Lab-Scripts/
  ```
- View the premade signature file:
  ```bash
  nl lab7_sec2-2.sig
  ```
- Process the PCAP file with the signature file:
  ```bash
  zeek -r ../Sample-PCAP/smallFlows.pcap -s ../Lab-Scripts/lab7_sec2-2.sig
  ```
- Open the generated `signatures.log` file to review results:
  ```bash
  gedit signatures.log
  ```

### **3. Modifying Zeek Signature Files**
- View the updated signature file to capture new traffic patterns:
  ```bash
  nl ../Lab-Scripts/lab7_sec3-1.sig
  ```
- Process the PCAP file using the modified signature file:
  ```bash
  zeek -r ../Sample-PCAP/smallFlows.pcap -s ../Lab-Scripts/lab7_sec3-1.sig
  ```
- Analyze the updated `signatures.log` for new matches:
  ```bash
  gedit signatures.log
  ```

### **4. Cleanup and Shutdown**
- Clear temporary log files generated during the analysis:
  ```bash
  ./../Lab-Scripts/lab_clean.sh
  ```
- Stop Zeek services to complete the session:
  ```bash
  cd $ZEEK_INSTALL/bin && sudo ./zeekctl stop
  ```

---

## Results
The lab demonstrated the utility of Zeek signatures in capturing and analyzing specific traffic patterns. Highlights included:
- Logs for HTTP POST and GET requests.
- Updates to capture DNS and SNMP request/response patterns.
- Insightful entries in `signatures.log` detailing matched signatures, triggered events, and corresponding packet payloads.

---

## Project Resources
- **Project Link**: [Introduction to Zeek Signatures](https://github.com/StephVergil/Introduction-to-Zeek-Signatures/blob/main/vNetLab07.docx.pdf)
- **Zeek Documentation**: [Zeek Documentation](https://docs.zeek.org/)
- **Sample PCAP Files**: [PCAP Samples](https://wiki.wireshark.org/SampleCaptures)
- **Zeek Signatures Overview**: [Zeek Signatures Framework Documentation](https://docs.zeek.org/en/master/frameworks/signatures.html)

---

## Conclusion
This project highlights the effectiveness of Zeek's signature framework for network traffic analysis. By defining and refining signature patterns, Zeek can efficiently identify and log network events, providing critical insights for security monitoring and threat detection. Mastery of these techniques enables enhanced network visibility and robust security posture.

---

## Disclaimer
This project was conducted in a controlled academic environment. Unauthorized use of these tools or techniques outside such an environment may violate ethical guidelines and legal regulations.
