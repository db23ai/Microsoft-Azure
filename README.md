
# 🌐 Azure Resource Group Management – CLI & PowerShell

This guide demonstrates how to **create**, **list**, and **delete** Azure Resource Groups using **Azure CLI** and **Azure PowerShell**, with annotated command examples.

## 📦 Prerequisites

- Azure CLI or Azure PowerShell installed.
- Logged in to Azure via `az login` or `Connect-AzAccount`.

---

## ⚙️ Azure CLI Commands

### ➕ Create a Resource Group

```bash
# Create a new resource group named "test-resource-group" in the "northeurope" region
az group create -l northeurope -n test-resource-group
```

<details>
<summary>📄 Example Output</summary>

```json
{
  "id": "/subscriptions/<sub-id>/resourceGroups/test-resource-group",
  "location": "northeurope",
  "name": "test-resource-group",
  "properties": {
    "provisioningState": "Succeeded"
  },
  "type": "Microsoft.Resources/resourceGroups"
}
```
</details>

---

### 📃 List All Resource Groups

```bash
# List all resource groups in your subscription
az group list
```

<details>
<summary>📄 Example Output (JSON)</summary>

```json
[
  {
    "name": "DEMO-RG",
    "location": "northeurope",
    "properties": {
      "provisioningState": "Succeeded"
    }
  },
  ...
]
```
</details>

---

### 📊 Display Resource Groups in Table Format

```bash
# Query and display only name and location in table format
az group list --query "[].{Name:name, Location:location}" --output table
```

🖥️ **Output:**

```
Name                 Location
-------------------  ------------
DEMO-RG              northeurope
test-resource-group  northeurope
NetworkWatcherRG     koreacentral
```

---

### ❌ Delete a Resource Group

```bash
# Delete the specified resource group
az group delete -n test-resource-group
```

📌 **Note:** Prompts for confirmation — type `y` to proceed.

---

## ⚙️ Azure PowerShell Commands

### ➕ Create a Resource Group

```powershell
# Create a new resource group in northeurope
New-AzResourceGroup -Name test-resource-group -Location northeurope
```

<details>
<summary>📄 Example Output</summary>

```
ResourceGroupName : test-resource-group
Location          : northeurope
ProvisioningState : Succeeded
ResourceId        : /subscriptions/<sub-id>/resourceGroups/test-resource-group
```
</details>

---

### ❌ Delete a Resource Group

```powershell
# Delete the specified resource group
Remove-AzResourceGroup -Name test-resource-group
```

📌 **Note:** Prompts for confirmation — type `Y` to confirm.

---

## 📚 Reference

📖 [Azure CLI: Manage resource groups](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-cli)
