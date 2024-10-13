# Network Addressing

## Class Information

**Class:** June 3, 2024

## Quick Tricks

### 0000

To recognize 192 in an IP Address, its:

`11000000`

## Switches vs. Routers

Routers are only when you want to go to the internet.

You can use a switch to create a local area network (LAN).

## NAT

Network Address Translation (NAT) is a way to map multiple private addresses inside a local network to a public IP address before trasnferring the information onto the internet.

## MAC Address

A MAC Address is a unique 48-bit hardware number of a computer, which is embedded into a network card (known as a Network Interface Card) during the time of manufacturing.

The MAC Address is also known as the Physical Address of a network device or the Hardware Address.

## IPv4 vs IPv6



## IPv4

**Example:** 192.168.26.1

**Format:** `xxx.xxx.xxx.xxx`

**Size:** 32-bit (divided into four octets, with each containing 8 bits; 4 bytes)

**Number of Addresses:** 4,293,967,296 (2^32)

**Classes:** `/8 | A`, `/16 | B`, `/24 | C`, `/32 | D`

#### Consists of two parts:

* Network (Represents the network part of the IP Address)

* Host (represents the specific device on the network)

### Limitations of IPv4

* Limited Address Space

* Address Exhaustion

* Lack of Built-In Security

* Limited Scalability

* Limited Support for QoS

* Lack of Support for Modern Technologies: struggles to meet demands of IoT and cloud computing

## Subnet Mask

**Broadcast Address:** 255.255.255.255

**Subnet Mask For Class C:** 255.255.255.0

A subnet mask is a 32-bit address, same as an IP Address. Like an IPv4 address, a subnet mask consists of four octets seperated by dots.

## Classful Network

> **History:** Began in 1981. Used until the introduction of classless inter-domain routing in 1993.

## IPv6

After awhile the IPv4 address space was depleted there needed to be more space. This introduced IPv6.

**Example:** `2001:0000:3238:0001:0063:0000:0000:FEFB`

### Compressing IPv6 Addresses

1. Leading Zeros: The first rule allows us to discard leading zeros in a block, making the address a bit shorter.
2. Consecutive Zeros: If two or more blocks contain consecutive zeros, they can be omitted and replaced with double colon signs (::) resulting in `2001:0:3238:1:63::FEFB`
3. Zero Block: if there is a block that consists of four zeros but without a consecutive zero-filled block, it can be replaced with a single zero, and the final address will be `2001:0:3238:1:63::FEFB`

### IPv6 Address Breakdown

In IPv6 addresses, the prefix represents the network portion of the address. IPv6 does not use notation subnet masks like IPv4. The prefix length indicates the network portion.

#### Structure

1. 2001:0ABC:00BB:
2. 0000
3. 0000:0000:0000:0001
4. /64

#### Info About Structure

1. Because the prefix is /64, the first 64 bits in the address represent the network portion
2. The 16 bits from the 49th to the 64th are for defining subnets
3. The remaining 64 bits represent the host portion in the IPv6 address.
4. The range can be from 0 to 128, with the most common being /64

## Configure & Verify IPv6

1. To enable IPv6 routing, enter the configuration terminal mode and run the `ipv6 unicast-routing` command.
2. Configure IPv6 on the router interface using the `ipv6 address`
3. Verify the configuration using the `show ipv6 interface brief`

### Anycast

In IPv6, its called **Anycast** instead of Broadcast.

### IPv6 Unicast Types

#### Global Unicast

IPv6 global unicast addresses are similar to IPv4 public addresses. They are unique and can be routed via the internet.

#### Link-Local

Addresses that enable communication between devices in the same local link (LAN).

Link-local addresses must be unique only within the link. They are not guaranteed to be unique beyond their network segment and begin with FE80::/10

#### Unique-Local

Similar to IPv4 private addresses with minor differences.

Unique addresses should not be routable in the global IPv6 and should not be translated to global IPv6 addresses. They begin with FC00::/8.

#### Common IPv6 Addresses

**Global Unicast:** `2001:0ABC:1111:0000:1111:0000:0000:0200` | The address range is from 2000 to 3FFFF

**Global Unicast:** `2001:0ABC:0000:00BB:DCBA:0000:0000:0200` | The address range is from 2000 to 3FFF

**Link-Local:** `FE80:0000:0000:0000:3211:5412:ECDC:FE11` | The link-local address prefix is FE80::/10

**Link-Local:** `FE80:0000:0000:0000:3211:5412:CAD1:FE12` | The link-local address prefix is FE80::/10

**Multicast:** `FF02:0000:0000:0000:0000:000F:FF00:120F` | Multicast addresses use the prefix `ff00::/8`

**Anycast:** `xxxx:xxxx:xxxx:xxxx:0000:0000:0000:0000 | Similar to broadcast addresses in IPv4

## IPv4 and IPv6 Coexistence

IPv4 and IPv6 can coexist using protocols and tools created by IETF, which are known as dual stack, tunneling, and translation.

### Dual Stack

Dual stack means that a device runs both IPv4 and IPv6 protocols simultaneously. Using two stacks allows both IP versions to coexist.

### Tunneling

Tunneling is used when IPv6 addresses are to be sent over IPv4 networks or vice versa. In this method, the IPv6 packet is encapsulated within an IPv4 packet.

### Translation

Translation allows IPv6 to communicate with IPv4-enabled devices using techniques similar to those utilized by NAT.

## Communication Types

1. Unicast
2. Multicast
3. Broadcast

### Unicast

The most basic form. One-to-One packet transfer from a device to another.

### Multicast

Single source communicates with multiple destinations. Uses Class D addresses.

**Reserved For Multicasting:** `224.0.0.0 - 239.255.255.255`

### Broadcast

When a packet is sent from one device on the network to all other devices on the network, using 255.255.255.255

## Link-Local

Link-local addresses, also known as APIPA addresses, are only valid for communication within the network broadcast domain.

The entire `169.254.0.0/16` address range is reserved for link-local.

If:

* The DHCP is not availabe

* The IP Address is not statically configured

The OS will randomly generate a **link-local address**. They are not guaranteed to be unique outside the network.

## Loopback Address

Loopback addresses represent the same interface in a computer. It is home. It is how the computer talks to itself. Most operating systems use `localhost` to represent the IPv4 loopback address of `127.0.0.1`.

### IP Protocol

An Internet Protocol that is a numerical label assigned to devices. These devices include devices connected to the internet.

The IP Address space is managed by [IANA](https://www.iana.org/) (Internet Assigned Numbers Authority). The American Registry for internet numbers is called [ARIN](https://www.arin.net/).

It is divided into five different geographical entities.

> **History:** You used to be able to buy IPv4 addresses

These are registered public addresses available on the internet.

### Public vs. Private

IP addresses are typically divded into two groups: **private** and **public**

### Private

Private IPs are non-unique addresses that can belong to one of three IP address ranges. They are used to create networks that do not communicate over the internet. The same private IPs can be found in multiple separate networks and are free to use.

### Public

Public addresses are used for communication over the internet. These IP addresses must be unique, require a fee, and be purchased from service providers. A router will typically have both a private and public IP.


# Application

## Burp Suite

Read [Burp Suite](https://portswigger.net/burp)

Read [RFC5280](https://www.rfc-editor.org/rfc/rfc5280) for X.509 Certificates and CAs.

### What It Does

Intercepts traffic using a CA Certificate to analyze HTTPS traffic. This can be used to analyze traffic including GET, POSTS and other requests.

