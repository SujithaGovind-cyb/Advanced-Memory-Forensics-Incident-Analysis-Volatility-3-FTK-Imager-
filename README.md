# Advanced Memory Forensics Incident Analysis Volatility 3 FTK Imager

This repository details a two-stage digital forensic project focused on memory acquisition and in-depth analysis to uncover signs of system compromise. Part 1 demonstrates the rigorous process of securing live memory evidence using FTK Imager, ensuring data integrity for court admissibility. Part 2 utilizes the advanced framework Volatility 3.0 to dissect the memory image, identify hidden processes, analyze network connections, and locate suspicious code injection, providing crucial intelligence for incident response and malware analysis. The project validates the critical role of memory forensics in detecting stealthy, fileless threats that often bypass traditional disk-based security controls.

### Skills Learned

Memory Acquisition & Integrity
- Utilizing professional tools (FTK Imager) to capture volatile system memory, ensuring integrity through checksum verification.

Memory Forensics (Volatility 3)
- Mastery of memory analysis techniques to extract critical artifacts (processes, network sockets, registry keys) from a compromised system's RAM dump.

Stealth Threat Detection
- Identifying suspicious or hidden processes and memory regions (malfind) that indicate potential malware presence or system compromise.

Incident Intelligence
- Extracting vital system data (e.g., operating system version, running services, command history) to reconstruct the state of the machine at the time of compromise.

Network Activity Analysis
- Correlating active network connections and open sockets within the memory image to identify communication channels established by malicious processes.

### Tools Used

- Memory Acquisition Tool: FTK Imager
- Memory Analysis Framework: Volatility 3.0
- Operating System: Windows (Target)
- Integrity Verification: Checksum Calculation (MD5/SHA1)

## Steps

The investigation was executed in two distinct, methodologically sound stages:

1. Memory Image Acquisition (FTK Imager)

- Tool Selection and Preparation: Utilized FTK Imager, a recognized industry standard, to capture a complete memory dump of the running system.
- Device Identification: Documented all relevant storage device information, including capacity, file system type, and model, to establish context for the evidence.
- Acquisition Execution: Performed the step-by-step acquisition process as detailed in the forensic plan, capturing the volatile memory image and storing it in a designated, secure location. (See Figure X.X - FTK Imager Acquisition Interface).
- Checksum Verification: Generated a checksum file for the acquired memory image to provide mathematical proof of integrity, forming the foundational pillar of the chain of custody.

2. Memory Artifact Analysis (Volatility 3.0)

- Process Analysis (pslist, psscan): Executed process listing commands to identify all running processes and threads. Specifically searched for hidden processes or abnormalities, which often indicate sophisticated malware.
- Network Connection Mapping (netscan): Analyzed the memory dump for active network sockets and connections, successfully identifying the communication channels established at the time of capture.
- System Service and Registry Analysis (servicelist, windows.registry.printkey): Extracted system service information and relevant registry keys to map out the system's configuration and identify potential persistence mechanisms established by an attacker.
- Malicious Code Identification (malfind): Employed the malfind plugin to examine memory sections for characteristics of injected or concealed code, raising concerns about potential malware presence or system compromise.
- Session and Version Information: Extracted the operating system version and active user sessions to precisely define the system environment and user context during the incident. (See Figure Y.Y - Volatility 3.0 Session Analysis Output).

Ref 1: Security Onion Case Events
