# Working with VMSS and Custom Images


## Step One - Create two virtual machines and install HTTPD

Run following playbook:

```
ansible-playbook 01-create-vms.yml --extra-vars "resource_group=myrg"
```

It will:
- create 2 virtual machines
- install HTTPD on both of them
- change index.html to contain **Image A** and **Image B** respectively

Copy and paste IP addresses of both VMs to the browser:

![Public IP Address](images/vmss-update-vms-ip-addresses.png)


You should see two different versions of VM:

![VM A](images/vmss-update-browser-vma.png)

and

![VM B](images/vmss-update-browser-vmb.png)


## Step Two - Capture Images from both Virtual Machines

Run second playbook to capture the images:

```
ansible-playbook 02-capture-images.yml --extra-vars "resource_group=myrg"
```

## Step Three - Create VMSS using Image A

In this step we will create following components:
- public IP address
- load balancer
- VMSS referring image A

Run following playbook:

```
ansible-playbook 03-create-vmss.yml --extra-vars "resource_group=myrg"
```

Check the IP address printed out at the end:

![Public IP Address](images/vmss-update-vmss-public-ip.png)

check that it works in the browser:

![VMSS Image A](images/vmss-update-browser-initial-vmss.png)

## Step Four - Update Image Reference in VMSS and Upgrade Instances

Run final playbook to replace image A with image B:

```
ansible-playbook 04-update-vmss-image.yml --extra-vars "resource_group=myrg"
```

Now press **F5** in the browser to reload page and see that image gas changed:

![VMSS Image B](images/vmss-update-browser-updated-vmss.png)


