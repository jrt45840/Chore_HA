# Chore_HA
Chores for Home Assistant

This will add you the ability to add chores into your home assistant setup. Even though this is more of a manual install it should only take you about 15 to 20 minutes to get fully setup and ready to deploy.

# Features
Dynamic sorting

Support up to 5 childern each having up to 99 chore and up to 20 rewards.

Parent approval system 

# How does it work
Chore is Red when it needs to be done. Chore turns blue and the parents will get a notification to confim or dismiss the chore when the child complets a chore. If parent confirm the chore it turns green and the child will get points. If the parent dismiss then the chore turns back to red until the child completes it again.
When a child get enough points they can claim a reward and the points will be deducted and the parents notified.

# How to Install
# Step 1
Open studio code server and you want to create a folder called "packages" in the homeassistant directory. and then you want to create 6 new files called ("child1.yaml", "child2.yaml", "child3.yaml", "child4.yaml", "Child5.yaml", "parent.yaml"). In the homeassistant directory create a file called "dashboards.yaml"
# Step 2
Copy and paste from each of the files on here to home assistant

  
