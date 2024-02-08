# Checkpoint4 Submission

- **COURSE INFORMATION:** CAA900
- **STUDENT’S NAME:** ADIMABUA TEDDY NWABUISI
- **STUDENT'S NUMBER:** 132420233
- **GITHUB USER ID:** 132420233-myseneca
- **TEACHER’S NAME:** ATOOSA NASIRI
  
# Table of Contents

1. [Part A - Creating Network Resources using Azure CLI](#header1)
2. [Part B -  Working with Azure CLI Bash](#header2)
3. [Part C - Network Review Questions](#header3)
4. [Part D - Creating Virtual Machines](#header4)
5. [Part E - Creating Custom Images](#Header5)
6. [Part F - Clean Up your Environment](#Header6)


## Creating Network Resources Using  Azure CLI

### Updated lines in the networkconfig.sh
``` bash 
RG_NAME="Student-RG-1202214"     # your student group
LOCATION="canadacentral"    # your location
ID="90"          #unique ID assigned to you

Student_vnet_name="Student-1202214-vnet"
Student_vnet_address="10.14.17.0/24"
Client_Subnet_name="Virtual-Desktop-Client"
Client_Subnet_address="10.14.17.0/24"

```

- **Question 1:** This determines whether a resource group with the name specified in the variable $RG_NAME exists in the Azure environment. If the resource group does not exist, the condition evaluates to true, and the script continues its execution.

- **Question 2 :** This line checks if a resource exists
`if [[ $(az network vnet list -g $RG_NAME -o tsv --query "[?name=='$vnet']") ]]`

``` bash
### This line of code was used to check if vnte exists befor creating it
echo "Check if it already exists ---"
if [[ $(az network vnet list -g $RG_NAME -o tsv --query "[?name=='$vnet']") ]]; then
    echo "exists!"
    az network vnet show -g $RG_NAME --name $vnet --query id 
else
    echo "doesn't exist!"
    # Code for creating the VNET
fi
```

-- **Question 3 :**

```bash
az network vnet create -g Student-RG-1202214 \
    --name Router-90 \
    --location canadacentral \
    --address-prefix 192.168.90.0/24
```

-- **Question 3 :** The bash command below is used on Azure Cli to create the subnet

```bash
az network vnet subnet create --name SN1 \
    -g Student-RG-1202214 \
    --vnet-name Router-90 \
    --address-prefix 192.168.90.32/27
```

## Working with Azure CLI Bash
-  [List-of-vnets]()

- [default-student-vnet]()

- ### Peering table
| AllowForwardedTraffic | AllowGatewayTransit | AllowVirtualNetworkAccess | DoNotVerifyRemoteGateways | Name                  | PeeringState | PeeringSyncLevel | ProvisioningState | ResourceGroup      | ResourceGuid                          | UseRemoteGateways |
|-----------------------|---------------------|---------------------------|---------------------------|-----------------------|--------------|------------------|-------------------|--------------------|---------------------------------------|-------------------|
| True                  | False               | True                      | False                     | RoutertoStudent       | Connected    | FullyInSync      | Succeeded         | Student-RG-1202214 | c759eefc-bac2-0b49-0345-ff853eb5984d | False             |
| True                  | False               | True                      | False                     | RoutertoServer        | Connected    | FullyInSync      | Succeeded         | Student-RG-1202214 | 643051b6-1413-08c2-36a0-057ba7f670e2 | False             |
| AllowForwardedTraffic | AllowGatewayTransit | AllowVirtualNetworkAccess | DoNotVerifyRemoteGateways | Name                  | PeeringState | PeeringSyncLevel | ProvisioningState | ResourceGroup      | ResourceGuid                          | UseRemoteGateways |
|-----------------------|---------------------|---------------------------|---------------------------|-----------------------|--------------|------------------|-------------------|--------------------|---------------------------------------|-------------------|
| True                  | False               | True                      | False                     | ServertoRouter        | Connected    | FullyInSync      | Succeeded         | Student-RG-1202214 | 643051b6-1413-08c2-36a0-057ba7f670e2 | False             |
| AllowForwardedTraffic | AllowGatewayTransit | AllowVirtualNetworkAccess | DoNotVerifyRemoteGateways | Name                    | PeeringState | PeeringSyncLevel | ProvisioningState | ResourceGroup      | ResourceGuid                          | UseRemoteGateways |
|-----------------------|---------------------|---------------------------|---------------------------|-------------------------|--------------|------------------|-------------------|--------------------|---------------------------------------|-------------------|
| True                  | False               | True                      | False                     | Student-Bastion1202214 | Connected    | FullyInSync      | Succeeded         | Student-RG-1202214 | 80623fb1-0ec4-084c-2266-25c3521d0b84 | False             |
| True                  | False               | True                      | False                     | StudenttoRouter        | Connected    | FullyInSync      | Succeeded         | Student-RG-1202214 | c759eefc-bac2-0b49-0345-ff853eb5984d | False             |


