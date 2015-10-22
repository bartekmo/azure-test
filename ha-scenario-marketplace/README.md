# HA Cluster Setup for PAYG boxes
Ths ARM template deploys a new VNet with a High Availability cluster of Barracuda NG Firewalls. A set of backend subnets will be created and routed via firewalls to provide segmentation.

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://azuredeploy.net/)

Template parameters:

| Name | Description
|:--- |:---|
|Directory and Subscription|Choose your Azure directory and Subscription for deployment|
|Resource Group|Choose your existing or create a new Resource Group for this deeployment. You can have only one deployment of this template per Resource Group.|
|Firewall Vm Name|Name of the primary firewall instance ("-ha" is added to form name of the secondary box)|
|Dns Name For Public IP|DNS for Cloud Service associated with firewall instances|
|Virtual Network Name|Name of the virtual network to create|
|Vnet Address Space|Virtual network address range. Must be big enough to accomodate all subnets (at least /23)|
|Gateway Subnet Name|Name of subnet for firewall instances. Note - you must not use a reserved "GatewaySubnet" name.| 
|Primary HA Box Ip|IP address of the active box|
|Secondary HA box IP|IP address of the secondary box(standby)|
|Location|Data center where the boxes are created|
|Vm Size|Size of the Azure instances used for firewalls|
|Number of Backend Subnets|Define how many backend subnets to create. They will be named "Subnet-TierX"|
|Admin Password|Initial password for root user on both boxes|
