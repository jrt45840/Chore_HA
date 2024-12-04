# Chore_HA  
**Chores for Home Assistant**  

Easily manage chores and rewards for your household using Home Assistant. This integration includes features like dynamic sorting, a point-based reward system, and a parent approval workflow. While the setup process is partially manual, it should take approximately 15–20 minutes to complete.  

---

## Features  
- **Dynamic Sorting**: Automatically sorts chores based on status.  
- **Multi-Child Support**: Manage up to **5 children**, each with up to **99 chores** and **20 rewards**.  
- **Parent Approval System**: Parents can confirm or dismiss chores via notifications.  


## Installation  

### Step 1: Install the prerequirements
**Hacs** with these cards
- `Button Card`
- `fold-entity-row`
- `custom layout card` 
---

### Step 2: Install 
1. Default install
   - Default child names (`Child 1`, `Child 2`, `Child 3`, ect)
      - Just copy every in the directory `Default Child` into `Home Assistant` directory exept for helpers goes in to the package Folder.

---

### Step 3: Edit script File
1. Open `script.yaml` file and customize:  
   - Replace **`notify.device`** with the appropriate device(s).  
     - Up to 5 devices can be included. They must support confirmable notifications.  
---


### Step 4: Create a Sensor Template  
1. Create a new helper using the following sensor template:  
   ```yaml
   "{{ now().strftime('%A') }}"

---

### Step 5: Update Configuration
1. Open the `configuration.yaml` file.
2. Add the following lines:
   ```yaml
   homeassistant:
     packages: !include_dir_named packages
   lovelace: !include dashboard.yaml

---

### Step 6: Restart Home Assistant  
1. Restart Home Assistant.  
2. Go to **Developer Tools** and check the configuration.  
   - If the check is green, your setup is ready to use.  
