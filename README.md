# Dynamic-NAT-Configuration

## This lab demonstrates how to configure dynamic NAT on a Cisco router.

### Topics covered:
- Inside and outside interfaces
- Dynamic NAT configuration
- NAT verification commands

## Step 1 — Configure Interfaces

interface g0/0/0

ip address 192.168.1.1 255.255.255.0

ip nat inside

no shutdown

exit

interface g0/0/1

ip address 200.1.1.1 255.255.255.0

ip nat outside

no shutdown

exit

## Step 2 — Create NAT Pool

ip nat pool PUBLIC_POOL 200.1.1.10 200.1.1.20 netmask 255.255.255.0

## Step 3 — Create ACL

access-list 1 permit 192.168.1.0 0.0.0.255

## Step 4 — Enable Dynamic NAT

ip nat inside source list 1 pool PUBLIC_POOL

## Step 5 — Verification

show ip nat translations

#### MORE ABOUT ME : https://www.linkedin.com/in/sanaa-el-habib-kahloul/ 
