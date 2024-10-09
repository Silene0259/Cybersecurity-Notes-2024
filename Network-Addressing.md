# Network Addressing

## Class Information

**Class:** June 3, 2024

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

### IP Protocol

An Internet Protocol that is a numerical label assigned to devices. These devices include devices connected to the internet.

The IP Address space is managed by [IANA](https://www.iana.org/) (Internet Assigned Numbers Authority). The American Registry for internet numbers is called [ARIN](https://www.arin.net/).

It is divided into five different geographical entities.

> **History:** You used to be able to buy IPv4 addresses

These are registered public addresses available on the internet.




# Application

## Burp Suite

Read [Burp Suite](https://portswigger.net/burp)

Read [RFC5280](https://www.rfc-editor.org/rfc/rfc5280) for X.509 Certificates and CAs.

### What It Does

Intercepts traffic using a CA Certificate to analyze HTTPS traffic. This can be used to analyze traffic including GET, POSTS and other requests.

