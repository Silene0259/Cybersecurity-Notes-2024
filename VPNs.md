# VPNs (Virtual Private Networks)

**Virtual Private Networks (VPNs)** allow secure connections by allowing a user to transmit data through a secure tunnel.

> A VPN allows a user to securely and discreetly connect to a private network over the internet. A VPN establishes an encrypted connection, known as a VPN tunnel, through which all internet traffic and communications are transmitted. As a result, the user data is safe and confidential.

## Types of VPNs

### Point-To-Point Tunneling Protocol (PPTP)

**Date Introduced:** 1996

PPTP was one of the first protocols designed for establishing virtual private networks and worked by encapsulating Point-to-Point Protocol packets in a TCP stream.

### L2F

L2F was designed to establish VPN tunnels for dial-up network access and addressed the main limitations of PPTP, which was its dependency on IP protocols and a weak encryption mechanism.

### Layer 2 Tunneling Protocol (L2TP)

**Date Introduced:** 1996

L2TP doesn't provide encryption on its own, so it's often combined with IPsec, known as L2TP/IPsec.

### OpenVPN

**Date Introduced:** 2001

Open-Source, publicly-available, easily adaptable.

OpenVPN utilized SSL/TLS for its primary authentication and encryption mechanism and could operate over both UDP and TCP transport layers.

### SSL VPNs

During the 2000s, VPN usage expanded beyond the limitations of dedicated software. SSL VPNs were developed using the SSL/TLS protocol and enabled users to securely access applications, data, and other resources on a network through VPN, only using their browser.

### Wireguard

Wireguard is a newer version of VPNs that uses more secure encryption and is more up-to-date while maintaining simplicity.

### Split Tunneling vs. Full Tunneling

Tunneling is a fundamental concept in VPN technology that allows data to be securely transmitted across an untrusted network, such as the Internet.

It involves encapsulating the original data within a secure "tunnel" or container, protecting it from potential eavesdropping or tampering.

#### Split-Tunneling

Split Tunneling: In a split tunneling configuration, only traffic intended for the corporate network or the VPN's destination is routed through the VPN tunnel. All other Internet-bound traffic is sent directly to the local Internet service provider (ISP). This setup allows users to access both the corporate network and the public Internet simultaneously.

**Pros:** Split tunneling can improve Internet speed since not all traffic is routed through the VPN, reducing potential congestion.

**Cons:** It can be less secure because only the traffic going through the VPN is protected. If a user inadvertently visits a malicious website or downloads malicious content, it won't go through the VPN's security measures.

#### Full-Tunneling

Full Tunneling: In a full tunneling configuration, all traffic from the user's device is routed through the VPN tunnel, including Internet-bound traffic. This means that every bit of data, even regular web browsing, is encrypted and sent through the corporate network.

**Pros:** Full tunneling provides a higher level of security as all traffic benefits from the VPN's encryption and security measures. It ensures consistent security policies for all network traffic.

**Cons:** It can potentially lead to slower Internet speeds due to the additional routing through the VPN.

#### Extra

The choice between split tunneling and full tunneling depends on the specific requirements and security policies of an organization.
