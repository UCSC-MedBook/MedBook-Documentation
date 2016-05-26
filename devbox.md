# Creating a Dev Box on Azure

### Create box

1. Click New to create a new box. 
2. Select Ubuntu Server 16.04LTS as the base image.
3. Name the box, paste your public key. Use `ubuntu` as the user name.
4. Select the `medbook-dev` resource group. West US for location.
5. On the size selection screen, click *View all* to see all of the available boxes. Select *A4 Standard* (8 cores 14GB memory) as the box type.
6. Leave the next settings page (Configure optional features) with the default values.
7. Launch

### Attach more storage
1. From the virtual machine settings pane, select *Disks*.
2. Set the size to 256GB and click OK.

### Provision with ansible
0. Wait until the disk is attached (should show up as a *data disk* under settings/disks.
1. Add the IP address to [dev] and [docker] sections of https://github.com/UCSC-MedBook/MedBook/blob/cloud-hosting/ansible/hosts
1. From the `MedBook/ansible` directory run `ansible-playbook playbook.yml -i hosts -u ubuntu`
2. Manually add the appropriate public keys to the box (TODO this should be automated by ansible)

### Set up MedBook
