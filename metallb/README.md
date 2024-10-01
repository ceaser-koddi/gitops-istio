# MetalLB

Update the ip-address-pool with the network for your system.
```bash
netpart=$(docker network inspect -f '{{.IPAM.Config}}' kind | grep -oP '\d+\.\d+\.\d+\.\d+' | awk -F'.' 'NR==1{print $1"."$2}')
echo "Network for LoadBalancer: ${netpart}.255.200-$netpart.255.250"
```
