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
- `layout-card`
- `fold-entity-row`
---

### Step 2: Install 
1. Default install
   - Default child names (`Child 1`, `Child 2`, `Child 3`, ect)
      - Just copy every in the directory `Default Child` into `Home Assistant`.
      - go to **step 3**.
2. Custom install
   - Custom child names
      - Open directory `Custom Name` and download the `ChoreHaAssistant.zip` extract the zip file and run `Chore HA Assistant.exe`.
      - Follow the directions in the program to continue.

---

### Step 3: Edit Child Files  
1. Open each `child#.yaml` file and customize:  
   - Replace **`notify.device`** with the appropriate device(s).  
     - Up to 5 devices can be included. They must support confirmable notifications.  
   - Adjust the **timeout** value (default is 15 minutes).  
     - If a notification is missed or dismissed, the script will retry until confirmation or dismissal is received.  

---

### Step 4: Update Parent Notification Device  
1. Open `parent.yaml` and scroll to **line 245**.  
2. Replace **`#Edit here`** with your parent device name.  
   - This name can be any recognizable device in your Home Assistant setup.  

---

### Step 5: Add Child Names  
1. Open `dashboards.yaml`.  
   - Replace placeholders marked **`#Edit Here`** with each child’s name.  
2. Open each `child#.yaml` file.  
   - Use **Find and Replace** to change all instances of **`Child #`** to the corresponding child’s name.  

---

### Step 6: Create a Sensor Template  
1. Create a new helper using the following sensor template:  
   ```yaml
   "{{ now().strftime('%A') }}"

---

### Step 7: Update Sensors in Child Files
1. Open each `child#.yaml` file.
2. Replace all instances of sensor.currentday with the name of the helper you created in Step 6.

---

### Step 8: Update Configuration
1. Open the `configuration.yaml` file.
2. Add the following lines:
   ```yaml
   homeassistant:
     packages: !include_dir_named packages
   lovelace: !include chores/dashboards.yaml

---

### Step 9: Restart Home Assistant  
1. Restart Home Assistant.  
2. Go to **Developer Tools** and check the configuration.  
   - If the check is green, your setup is ready to use.  
3. If you encounter the following warning:  

   ```plaintext
   Configuration warnings  
   Setup of package 'child1' failed: Integration 'views' not found.  
   Setup of package 'child2' failed: Integration 'views' not found.  
   Setup of package 'child3' failed: Integration 'views' not found.  
   Setup of package 'child4' failed: Integration 'views' not found.  
   Setup of package 'child5' failed: Integration 'views' not found.  
   Setup of package 'parent' failed: Integration 'views' not found.

   This is normal the package integration doesn't allow views to be implemented. But the dashboards.yaml file makes up for the views. Just ignor this warning.
