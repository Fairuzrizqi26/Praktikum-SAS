# Lab Report 1
# Practicum Module 1 Virtualisasi - Sistem Administrasi Server

**From Group 6 [ IT 02-01 ]**

**Fairuzrizqi Nugraharsanto   1202190044 || Budhi Priambodo  1202192065**

------
**Case Study**
------
Create an basic virtualization as a company profile website based on domain strategy that has explain by CTO.

- vm.local
  - Containing Landing Page
- vm.local/blog
  - Containing Blog
- vm.local/app
  - Containing Enterprise App

## Scheme
![soal_praktikum](https://user-images.githubusercontent.com/92350603/138592249-bff00a04-bb65-47b8-91ee-e52bb9a4a634.png)

| Server Name                    | IP         | Domain                 |
| ------------------------------ | ---------- | ---------------------- |
| LXC ubuntu server 18.04 php7.4 | 10.0.3.101 | http://lxc_php7.dev    |
| LXC debian server 9 php5.6     | 10.0.3.102 | http://lxc_php5.dev    |
| LXC ubuntu server 16.04        | 10.0.3.103 | http://lxc_landing.dev |

## Problem Solving

#### Make sure the bridge adapter and Ip Static settings
![rte](https://user-images.githubusercontent.com/92350603/138592469-b73fac4c-d06b-4e93-955b-abbfabf1199b.png)
#### Check the existing LXC from the previous practicum
![2](https://user-images.githubusercontent.com/92350603/138592631-aad43757-b8e5-4104-8757-38e0925704a3.png)

*Log in to super user with using command `sudo su`*

1. Rename ubuntu_php5.6 to ubuntu_landing, also change the IP following the new scheme

   Type
   ```
   lxc-copy -R -n ubuntu_php5.6 -N ubuntu_landing
   ```
This code is for copy than changing the container name from ubuntu_php5.6 to ubuntu_landing.
![3](https://user-images.githubusercontent.com/92350603/138592636-d4939acf-ca96-4370-bef3-5e48a7312dca.png)

To make sure the name of ubuntu_php5.6 has changed, we can check using the command
   ```
   lxc-ls -f
   ```
If the container name has changed to ubuntu_landing, we have to change the IP from before to a new one following the new scheme
We need to start the container first (Ubuntu_landing and ubuntu_php7.4)
   ```
   lxc-start -n ubuntu_landing
   lxc-start -n ubuntu_php7.4
   ```
![4](https://user-images.githubusercontent.com/92350603/138593288-6ec8b081-e418-491e-ba9b-42f967484ee7.png)

after that go to ubuntu landing
   ```
   lxc-attach -n ubuntu_landing
   ```
After we enter the root, we need to set the IP following the new scheme
   ```
   nano /etc/network/interfaces
   ```
Then we will see this interface
   ```
   nano /etc/network/interfaces
   ```
Then Change ip ubuntu landing `10.0.3.102` to `10.0.3.103`

![5](https://user-images.githubusercontent.com/92350603/138593747-ab81df4e-c149-4078-a985-deff71f61d9b.png)

then restart ip `systemctl restart networking.service`. and check ip using `ifconfig`

![6](https://user-images.githubusercontent.com/92350603/138593888-9ae458ac-5901-4444-a562-49b7e1c98267.png)

exit ubuntu_landing

![7](https://user-images.githubusercontent.com/92350603/138593930-e0d2333c-3f91-40e9-8e0c-a18b13c743b4.png)

2. Install LXC Debian 9 with the name ubuntu_php5.6
type
   ```
   sudo lxc-create -n debian_php5.6 -t download -- --dist debian --release stretch --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org
   ```
Then check your container `lxc-ls -f`

![9](https://user-images.githubusercontent.com/92350603/138594104-e140a072-57fb-4c3f-8f63-d895845d755c.png)

3. Setup debian_php5.6 nginx to it's domain `http://lxc_php5.dev`, then make index.html page that explains lxc names information
Start debian_php5.6 
   ```
   lxc-start -n debian_php5.6
   lxc-attach -n debian_php5.6
   ```
Then instal nginx and net tools
   ```
   apt install nginx nginx-extras
   apt install nano net-tools curl
   ```
Afterthat Setting ip static debian_php5.6
   ```
   nano /etc/network/interfaces
   ```
   
![10](https://user-images.githubusercontent.com/92350603/138594612-a3e88c94-1c19-4512-8f39-a460f4c750ac.png)

then restart ip `systemctl restart networking.service`. and check ip using `ifconfig`

![11](https://user-images.githubusercontent.com/92350603/138594724-563f77be-ad92-4e85-b992-4a52664d5e46.png)

After that we need to set the nginx

![12](https://user-images.githubusercontent.com/92350603/138594807-9adeca28-6feb-49e5-b932-afc354b6db4b.png)

Enter the nano for configuration 

   ```
   nano lxc_php5.6.dev
   ```

![13](https://user-images.githubusercontent.com/92350603/138594893-b04e58bb-b0ea-4ac7-927e-93c53bd7ed91.png)

Nginx acts as a bridge for containers and the internet

![14](https://user-images.githubusercontent.com/92350603/138594973-6cb53ce3-ee34-4084-ab79-fb4ec69fb1ad.png)

Then we need to configure the hosts

   ```
   nano /etc/hosts
   ```
   
![15](https://user-images.githubusercontent.com/92350603/138595020-81afa473-1d2a-446a-8c8f-3354a08295da.png)

After we save it then we need to enter the directory for html
   ```
   cd /var/www/html
   mkdir lxc_php5.6
   cp index.nginx-debian.html lxc_php5.6/index.html
   cd lxc_php5.6
   nano index.html
   ```
   
![17](https://user-images.githubusercontent.com/92350603/138595109-c2a85f05-37b4-4c51-a70d-caafd51f8cfb.png)

After that, we need to check if the code that we type in index.html
   ```
   curl -i http://lxc_5.dev
   ```
![18](https://user-images.githubusercontent.com/92350603/138595168-2de4b478-762e-4c0f-8b0f-4bbff7fe05ca.png)

and it works, then exit

4. Setup ubuntu_landing nginx to it's domain `http://lxc_landing.dev`, then make index.html page that explains lxc names information. for the step like no 3

![19](https://user-images.githubusercontent.com/92350603/138595389-4abb1f9d-2da3-43d6-9c09-c3d10b78b27a.png)

![20](https://user-images.githubusercontent.com/92350603/138595393-60bc341a-b235-4903-8320-b510bde372ea.png)

![21](https://user-images.githubusercontent.com/92350603/138595404-84a2bff1-5d47-4224-b436-8a7f653827b1.png)

![22](https://user-images.githubusercontent.com/92350603/138595408-19a86270-979c-4a9a-8a7f-db3b5133ceda.png)

Code in index.html just like this

![23](https://user-images.githubusercontent.com/92350603/138595410-431c0a2a-7b42-4674-b42a-66e66908f3ae.png)

Than check with command curl
   ```
   curl -i http://lxc_landing.dev
   ```
![24](https://user-images.githubusercontent.com/92350603/138595414-5e0dcbe5-ea5e-4e06-aca9-172cb43caa38.png)

5.  LXC ubuntu_landing need to be 'auto start' when we turn on vm. We need to enter super user to enter config page
Go to the /var/lib/lxc directory and check if there are any directories

![25](https://user-images.githubusercontent.com/92350603/138595746-2f40e4c8-f82c-48fb-97d3-49eb095e868c.png)

Because it will use auto start on ubuntu landing, add config like below

![26](https://user-images.githubusercontent.com/92350603/138595766-76781473-0e8c-48b5-8ea6-4a5285dc224e.png)

Check auto start and rebooting first

![27](https://user-images.githubusercontent.com/92350603/138595828-3daa8e43-83e6-418c-9841-122016fecd39.png)

6. Setup nginx for vm.local to config the proxy_pass
Setup nginx on local vm
   ```
   sudo nano /etc/hosts
   ```
![28](https://user-images.githubusercontent.com/92350603/138595909-8d7133cb-b140-42da-9681-91e254aac727.png)

![29](https://user-images.githubusercontent.com/92350603/138595942-863d2c93-52aa-4dcf-984d-528ecb6c773f.png)

After that we need to install nginx, then enter the directory of sites available, then enter the nano of vm.local

![30](https://user-images.githubusercontent.com/92350603/138596030-1b44c414-0d10-4e25-913e-78014efdd1bd.png)

Edit the nano vm.local

![31](https://user-images.githubusercontent.com/92350603/138596052-9ae857b8-ee00-4759-bdab-763f34d47b05.png)

To check the html code appears as it should or not, use the curl command, curl is a command line tool to transfer data to or server, using any of the supported protocols like HTTP, FTP, etc.
 
   ```
   curl -i http://vm.local/
   ```
![32](https://user-images.githubusercontent.com/92350603/138596333-786249d2-5c2a-4d0a-9492-81e2fee553b0.png)

   ```
   curl -i http://vm.local/app
   ```
![33](https://user-images.githubusercontent.com/92350603/138596334-f0c9212b-2e7f-4511-a2cf-0e1fbec9be6f.png)

   ```
   curl -i http://vm.local/blog
   ```

![34](https://user-images.githubusercontent.com/92350603/138596336-fe1f4027-3163-4dbf-a0ed-3a363218c79d.png)

7. Access the vm.local in web browser, the output should be like this

   ```
   http://vm.local/
   ```
![35](https://user-images.githubusercontent.com/92350603/138596426-bdb9ef58-b4b2-49b5-b7b3-493466933003.png)

   ```
   http://vm.local/app
   ```
![37](https://user-images.githubusercontent.com/92350603/138596437-8a0fd717-84c8-42ba-92bf-91f2b44ef0c8.png)

   ```
   http://vm.local/blog
   ```
   
![36](https://user-images.githubusercontent.com/92350603/138596434-0a6ae5d5-b0ea-43ea-b2cb-6015e34b5402.png)

-------

### Analysis
- Why for the needs of php5.6 can not use ubuntu 16.04, so it needs to change the os to debian 9?
- Why use LXC virtualization on the website schema that will be developed?
- What is a proxy server? why can we think of vm.local as a proxy server?
### Answer
- Because php5.6 can't update, so we're using Debian 9, which is still working
- Because LXC is a lightweight virtualization system that can be accessed for free. The LXC system also provides frequently used command lines such as Create, Start, and Delete.
- **Proxy server** is a system that have a intermediary function for computer to access the internet. **vm.local** can be assumed as a Proxy Server because vm.local's just a bridge to proceed to the container app. So we can access the container as vm.local.

--------
