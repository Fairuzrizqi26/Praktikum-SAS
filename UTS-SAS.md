# UTS-Sistem Administrasi Server
------
## Fairuzrizqi Nugraharsanto 1202190044    IT0201
------
**Question**
------
<img width="461" alt="bbbb" src="https://user-images.githubusercontent.com/92350603/143621126-49a7a818-0d3d-4a3f-b737-ff4fafdae37f.PNG">

**Answer**
------
### A. Instalasi windows server 2022

Download ISO Installer windows server 2022

   https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022
   
   Select download the `ISO` then follow it step by step.
   
   <img width="874" alt="cccc" src="https://user-images.githubusercontent.com/92350603/143621513-6da949ad-311d-4c4b-af20-f8dc3031a9e4.PNG">

- Then open `Oracle VM`
   ![1](https://user-images.githubusercontent.com/92350603/143668175-186b26b6-fa01-42bc-930a-df88721c111b.png)
- Next Klik `New`, and do it like the picture below :
  
  Enter the name of the machine and type of system to use
![Screenshot (170)](https://user-images.githubusercontent.com/92350603/143668255-57a3ee73-6add-46c9-994f-b7cab295a81b.png)

- Define ram, create the disk defining type and size

![Screenshot (171)](https://user-images.githubusercontent.com/92350603/143668258-5d2c86fa-b905-4c63-9810-9bbce118862e.png)
![Screenshot (172)](https://user-images.githubusercontent.com/92350603/143668259-4d234602-23bb-42f5-8a82-7cbbcf4945dc.png)
![Screenshot (173)](https://user-images.githubusercontent.com/92350603/143668262-8b3dd91f-09be-4590-8732-c4bfa26474fc.png)
![Screenshot (174)](https://user-images.githubusercontent.com/92350603/143668265-5764bd8f-3adb-4165-a7c5-9dabd770f1ad.png)
![Screenshot (175)](https://user-images.githubusercontent.com/92350603/143668483-c983e7a3-ad2c-4394-9a29-dca5a3ff388f.png)

- Go to the machine configuration and in the `Network` section set `Bridge adapter`
![Screenshot (193)](https://user-images.githubusercontent.com/92350603/143668838-8b38e77e-4498-4ddd-aa3f-4534fa63e15e.png)

-  Click on `Start` and select the `ISO downloaded`

<img width="440" alt="ss 2" src="https://user-images.githubusercontent.com/92350603/143668979-b62bb549-febb-4b8c-9b5f-52e0957f0ca7.PNG">

-  Click on `Start` and the Windows Server 2022 installation wizard will load

![3](https://user-images.githubusercontent.com/92350603/143669454-108d765d-567f-4743-8a26-c1f0ac8b504c.png)

-  Click on `Install now`
![4](https://user-images.githubusercontent.com/92350603/143669176-71abffb1-c05f-4335-9b38-05327799b9c8.png)
![5](https://user-images.githubusercontent.com/92350603/143669179-8ff573b6-c55b-4678-bd41-89a82a2df513.png)

- Select windows server 2022 desktop experience
<img width="506" alt="6" src="https://user-images.githubusercontent.com/92350603/143669395-d74321e5-08fd-450b-bce1-a63c48f644b1.PNG">

- Accept the license and then proceed with the installation of Windows Server 2022

<img width="503" alt="7" src="https://user-images.githubusercontent.com/92350603/143669400-41460892-0627-4492-bbc7-7f2928cb5d45.PNG">

- Select windows server 2022 install microsoft server advanced (Custom)
![Screenshot (194)](https://user-images.githubusercontent.com/92350603/143669634-aa637eb7-2405-4b37-a19e-99c50d6ecc77.png)
- Location installation of windows server 2022
![Screenshot (193)](https://user-images.githubusercontent.com/92350603/143669804-5873d2d1-a9b8-452f-8eb8-8b41e86998ce.png)
- installation progress
![Screenshot (194)](https://user-images.githubusercontent.com/92350603/143669813-26f248c7-3902-47b8-87f3-7eecf5a74a3e.png)
- The system will reboot to complete the process
![Screenshot (181)](https://user-images.githubusercontent.com/92350603/143669880-65f30db7-2d28-4c6f-8e7a-4deabfe9927d.png)
- Next, custom your password administrator
![Screenshot (185)](https://user-images.githubusercontent.com/92350603/143669853-dec3a54e-15ac-4b0d-ad6e-313a0acc6f87.png)
- Access the menu `Input – Keyboard – Insert Ctrl + Alt + Del`. Enter the password created and wait for the configuration to load
![Screenshot (186)](https://user-images.githubusercontent.com/92350603/143669952-dec5d170-6ade-48d1-a7d8-44e54850f999.png)
![Screenshot (188)](https://user-images.githubusercontent.com/92350603/143669953-4ad35bca-86ca-4e6f-894b-2e4a8b30319f.png)
- Windows Server 2022 has been successfully installed
![Screenshot (190)](https://user-images.githubusercontent.com/92350603/143669993-270c8b54-79d5-4b96-b850-60187c0fbc60.png)
![Screenshot (192)](https://user-images.githubusercontent.com/92350603/143669994-66347623-61d4-47ff-8da6-81ac6bf481f9.png)

### B. Instalasi Active Directory Domain Services
-  Before doing the installation, we change the computer name first by going to windows powershell.
   Then type `rename-computer -Newname Server2022`
      - Open the start menu and select `Windows PowerShell`
   ![b1](https://user-images.githubusercontent.com/92350603/143672373-95676423-bec2-4003-b4a8-600b2fa47e57.png)
   ![b2](https://user-images.githubusercontent.com/92350603/143672377-f95ba41c-982b-4d7d-a578-1cea0feb48df.png)
      - Then Restart, and open`Server Manager` 
   ![b3_LI](https://user-images.githubusercontent.com/92350603/143672804-98d4848e-4333-428c-aa2f-a7b97bde3af7.jpg)
      - Select Menu `manage`, Then `Add Rules and Features` 
   ![b4_LI](https://user-images.githubusercontent.com/92350603/143672810-4e815c4e-9b7b-4f23-ad5c-bf90309b8760.jpg)
      - Select Next
   ![b5](https://user-images.githubusercontent.com/92350603/143672818-314608b0-2b3c-48d8-b4b5-63cfab465194.png)
      - Select option`Role-based or feature-based installation`. And `Next`
   ![b6](https://user-images.githubusercontent.com/92350603/143672828-ad7df85c-d33e-4b9b-a7d5-b3e2b8e4afc7.png)
      - Click `Select a server from the server pool` to select a local storage directory. Then `Next`
   ![b7](https://user-images.githubusercontent.com/92350603/143672831-8bcde095-899a-4445-bb3c-fd18b218d6b8.png )
      - Next, put a check mark in the `Active Directory Domain Services` box. When you check the box, on the right appears 
        a brief description of ADDS and how it works. Then click `Add Features`.
   ![b8_LI](https://user-images.githubusercontent.com/92350603/143672842-2095b4a2-0c0b-4bd8-b554-17fc3b6672d7.jpg)
   
   
### C. Instalasi DNS server
   - We need to install and configure the Active Directory role and DNS server to work together.
     Checklist `DNS Servers` then `add features` 
   ![c1](https://user-images.githubusercontent.com/92350603/143673100-618da08a-4061-4ff8-8f93-e45804fbd684.png)
   ![c2](https://user-images.githubusercontent.com/92350603/143673102-dc2f10f3-941c-41c2-b5a2-f5104756f0bb.png)

### D. Instalasi Net Framework 3.5
   - Checklist `.NET Framework 3.5 features`
   ![d1](https://user-images.githubusercontent.com/92350603/143673121-ebd2d23b-fbbc-42a8-bef3-174df70a8e4c.png)
   - Click `Next`
   ![d2](https://user-images.githubusercontent.com/92350603/143673125-610cecfa-c216-495c-82fa-50656f45392f.png)
   - Click `Next`again
   ![d3](https://user-images.githubusercontent.com/92350603/143673126-12ffae73-67d1-4457-a862-91fa04bfa751.png)  
   - Select `Install`
   ![d4](https://user-images.githubusercontent.com/92350603/143673128-44a956b8-9e96-4ec3-b8ae-4923fc17d55e.png)
   - And Success `Yeahhh`
   ![d5](https://user-images.githubusercontent.com/92350603/143673130-65ad3618-61a3-4134-b0d7-9f2ef66f07ed.png)

### E. Promote Server to a Domain Controller
-  Setting to static ip using `cmd`, type `sconfig`
-  Setting the IP Address Server-ADDS and pointing the DNS to the static IP address used.
-  Click `Promote this server to a domain controller` for ADD configuration
-  Select `Add a new forest` and enter the domain name to be used in the Root Domain Name. For example here I use the domain `Aim.com`
-  Select `Windows Server 2016` at the functional level, put a check mark on `Domain Name System (DNS) server` and `Global Catalog (GC)`. 
   And fill in the Directory Services Restore Mode password with strong password criteria.
-  then click `Next`
-  Fill in `The NetBIOS domain name` according to the domain name used.
-  Skip the Paths section, click `Next`.
-  Check the configuration specified in `Review Options`, if it is TRUE. Click `Next`.
-  If there is `All prerequisite checks passed successfully.` Click `Install` to apply the specified configuration.
-  After the installation is complete, the laptop will restart automatically. Then login using administrator password
-  To check the configuration results, open cmd and type `netdom query fsmo`
-  After logging in with the Active Directory Domain Controller, open the TCP/IP properties of your network connection. 
   You can see the DNS server IP Address.
-  ^_^ DONE ^_^  
 *GAMBAR MENYUSUL LURRR*








