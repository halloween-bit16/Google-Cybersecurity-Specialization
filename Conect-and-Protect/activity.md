# Incident Report Analysis

## Summary

The organization experienced a Denial-of-Service (DoS) attack that disrupted internal network operations for approximately two hours. A malicious actor flooded the network with ICMP packets through an improperly configured firewall, overwhelming network resources and preventing legitimate users from accessing services. The incident response team mitigated the attack by blocking incoming ICMP traffic, taking non-critical services offline, and restoring critical services. Following the investigation, the organization implemented firewall rate limiting, source IP verification, network monitoring software, and an IDS/IPS solution to reduce the risk of similar attacks in the future.

---

## Identify

**Type of attack:** Denial-of-Service (DoS) attack using ICMP flooding (Ping Flood).

**Affected systems:**

* Internal network infrastructure
* Network services
* Firewall configuration
* Business operations relying on network connectivity

**Root cause:**

* Unconfigured firewall allowed excessive ICMP traffic into the network.
* Lack of monitoring and intrusion detection capabilities.

---

## Protect

To better protect organizational assets, the company should:

* Maintain firewall rules that limit incoming ICMP traffic.
* Implement source IP verification to reduce IP spoofing attacks.
* Regularly audit firewall configurations and network devices.
* Apply the principle of least privilege for network administration.
* Conduct employee cybersecurity awareness training.
* Keep network devices and security software updated.
* Use IDS/IPS technology to automatically block suspicious traffic.

---

## Detect

To improve detection of future incidents, the organization should:

* Use network monitoring software to identify unusual traffic patterns.
* Deploy an IDS to detect suspicious ICMP traffic and other attacks.
* Enable firewall logging and review logs regularly.
* Implement a SIEM solution to centralize and analyze security events.
* Monitor network bandwidth usage for abnormal spikes.
* Generate automated alerts for unusual network activity.

---

## Respond

If a similar incident occurs in the future, the organization should:

* Immediately identify and isolate affected systems.
* Block malicious traffic at the firewall.
* Disable or limit non-essential services during the attack.
* Preserve logs and network traffic data for investigation.
* Notify management and relevant stakeholders.
* Analyze the attack source, methods, and affected systems.
* Update security controls and response procedures based on lessons learned.

---

## Recover

To recover from future incidents, the organization should:

* Restore affected network services and systems to normal operation.
* Verify that systems are functioning correctly before returning them to production.
* Review firewall configurations and security controls.
* Maintain backup copies of critical configurations and system data.
* Document lessons learned and update recovery procedures.
* Communicate recovery status to employees, management, and affected stakeholders.

---

## Reflections/Notes

This incident demonstrated the importance of properly configuring firewalls, continuously monitoring network traffic, and implementing layered security controls such as IDS/IPS systems. Regular security audits and proactive monitoring can help identify vulnerabilities before they are exploited by attackers.
