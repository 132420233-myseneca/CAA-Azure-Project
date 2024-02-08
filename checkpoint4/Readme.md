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

- - **Question 3 :**

```bash
az network vnet create -g Student-RG-1202214 \
    --name Router-90 \
    --location canadacentral \
    --address-prefix 192.168.90.0/24
```

