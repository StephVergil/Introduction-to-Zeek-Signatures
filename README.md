# Introduction to Zeek Signatures

This project focuses on utilizing Zeek's signature framework to create pattern-based filters for efficient network traffic analysis. The lab explores creating and modifying signature files, analyzing network traffic for specific patterns, and generating detailed logs for matched signatures. 

### Objectives
- Start and configure Zeek for signature-based network traffic analysis.
- Execute premade Zeek signature files to match HTTP traffic patterns.
- Modify Zeek signature files to identify specific UDP-based SNMP and DNS messages.
- Analyze logs to interpret matched signatures and their corresponding events.

### Tools Used
**Zeek**: For creating and executing signature-based network analysis.  
**Sample PCAP Files**: Used as test data for signature matching.  
**Gedit**: For viewing and editing signature files and logs.

### Key Steps
1. **Starting Zeek**: Initialize Zeek using the following command:  
   `cd $ZEEK_INSTALL/bin && sudo ./zeekctl start`
2. **Executing Premade Zeek Signatures**:
   - Navigate to the **Lab-Scripts** directory:  
     `cd ~/Zeek-Labs/Lab-Scripts/`
   - View the premade signature file:  
     `nl lab7_sec2-2.sig`
   - Process the PCAP file using the premade signature file:  
     `zeek -r ../Sample-PCAP/smallFlows.pcap -s ../Lab-Scripts/lab7_sec2-2.sig`
   - View the generated `signatures.log` file:  
     `gedit signatures.log`
3. **Modifying Zeek Signature Files**:
   - View the updated signature file:  
     `nl ../Lab-Scripts/lab7_sec3-1.sig`
   - Process the PCAP file using the updated signature file:  
     `zeek -r ../Sample-PCAP/smallFlows.pcap -s ../Lab-Scripts/lab7_sec3-1.sig`
   - Analyze the new `signatures.log` file for updated signature matches:  
     `gedit signatures.log`
4. **Cleanup and Shutdown**:
   - Clear temporary log files:  
     `./../Lab-Scripts/lab_clean.sh`
   - Stop Zeek:  
     `cd $ZEEK_INSTALL/bin && sudo ./zeekctl stop`

### Results
The analysis demonstrated the functionality of Zeek signatures to capture specific traffic patterns and log details. Logs were generated for HTTP POST and GET requests and updated to capture DNS and SNMP request/response patterns. The `signatures.log` provided insights into matched signatures, triggered events, and packet payloads.

### Project Resources
- **Project Link**: [Introduction to Zeek Signatures](https://github.com/StephVergil/Introduction-to-Zeek-Signatures/blob/main/vNetLab07.docx.pdf) 
- [Zeek Documentation](https://docs.zeek.org/)
- [PCAP Samples](https://wiki.wireshark.org/SampleCaptures)

### Conclusion
This lab highlights the effectiveness of Zeek signatures for network traffic analysis. By leveraging pattern matching, Zeek signatures can identify packets following predefined formats, enabling rapid detection and efficient analysis of network events.

### Disclaimer
This project was conducted in a controlled environment. Unauthorized use of these techniques or tools outside such an environment may violate ethical guidelines and legal regulations.
