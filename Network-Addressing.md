# Network Addressing

## Class Information

**Class:** June 3, 2024

## Quick Tricks

### 0000

To recognize 192 in an IP Address, its:

`11000000`

## IPv4 vs IPv6



## IPv4

**Example:** 192.168.26.1

**Format:** `xxx.xxx.xxx.xxx`

**Size:** 32-bit (divided into four octets, with each containing 8 bits)

**Number of Addresses:** 4,293,967,296 (2^32)

**Classes:** `/8 | A`, `/16 | B`, `/24 | C`, `/32 | D`

#### Consists of two parts:

* Network (Represents the network part of the IP Address)

* Host (represents the specific device on the network)

## Subnet Mask

**Broadcast Address:** 255.255.255.255

**Subnet Mask For Class C:** 255.255.255.0

A subnet mask is a 32-bit address, same as an IP Address. Like an IPv4 address, a subnet mask consists of four octets seperated by dots.

## Classful Network

> **History:** Began in 1981. Used until the introduction of classless inter-domain routing in 1993.

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

