Each AWS [[Subnet]]  must reside entirely within one Availability Zone and cannot span zones. By launching AWS resources in separate Availability Zones, you can protect your applications from the failure of a single Availability Zone.

3 Subnet types
- Public
- Private
- VPN-only .The subnet does not have a route to an internet gateway. Just site to site


Each subnet must be associated with a route table, which specifies the allowed routes for outbound traffic leaving the subnet. Every subnet that you create is automatically associated with the main route table for the VPC.

IP setting
- Auto assign
- Resource-based name(RBN) settings

For security view [[AWS ACL]]