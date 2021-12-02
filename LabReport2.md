# **Praktikum Modul 2**

### Fairuzrizqi Nugraharsanto (1202190044)
### Budhi Priambodo (1202192...)

---

1. Rubah LXC landing dengan ubuntu focal (destroy n create, same ip, same name)

   * Cek lxc dengan menggunakan 

   ```markdown
    lxc-ls -f
   ```
   ![1](https://user-images.githubusercontent.com/92350603/144398558-b12ea29e-3d6f-4f9a-a1ce-e7dc203f084f.png)

   

   * Hapus ubuntu landing dengan menggunakan  command seperti dibawah ini, dan buat ubuntu focal baru dengan lxc-create

   ```markdown
    lxc-destroy ubuntu_landing
   ```
   ![2](https://user-images.githubusercontent.com/92350603/144399349-fd64ed4b-f22e-4861-92ed-7cde94e5c75c.png) 
   ![3](https://user-images.githubusercontent.com/92350603/144399542-90ebf4f8-130d-410c-8ff5-f4e9eec5861c.png) 


- Setelah membuat baru, gunakan command lxc-start untuk memulai ubuntu_landing dan gunakan command lxc-attach untuk membuka ubuntu_landing. Lalu gunakan install nano untuk mengedit config.
  
  ![4](https://user-images.githubusercontent.com/92350603/144399608-29608414-e7c8-40ee-bbca-594019c96509.png)

- Atur IP ubuntu_landing
  ```markdown
  sudo lxc-start -n ubuntu_landing
  sudo lxc-attach  -n ubuntu_landing
  nano /etc/netplan/10-lxc.yaml
  netplan apply
  ```
   ![5](https://user-images.githubusercontent.com/92350603/144399632-b3be7ef6-cb97-478f-b2a5-6569350ae8d5.png)
   ![6](https://user-images.githubusercontent.com/92350603/144399973-afa6e4d1-657b-4b79-9b8f-d5ba4e1b6488.png)

  - atur autostart lxc, seperti dibawah ini :
  
   ![7](https://user-images.githubusercontent.com/92350603/144399948-000a0297-e113-4f34-9942-a389c82e0d4e.png)

  - install ssh 
  
   ![8](https://user-images.githubusercontent.com/92350603/144400034-869b66b0-5004-4738-9d0b-ebcf27531ceb.png)

    ```markdown
    PermitRootLogin yes
    RSAAuthentication yes
    service sshd restart
    
    ```
    
    ![9](https://user-images.githubusercontent.com/92350603/144400117-af8adfc4-a4b3-435c-b9ec-23b8ba034a16.png)


  - cek ssh apakah sudah berjalan atau belum

    ![10](https://user-images.githubusercontent.com/92350603/144400147-0ff14676-95d9-4f69-8f92-82276b886c57.png)



2. Rubah LXC php7 dengan ubuntu focal (destroy n create, same ip, same name)

   - Cek lxc dengan menggunakan 

   ```markdown
    lxc-ls -f
   ```

   * Hapus ubuntu landing dengan menggunakan  command seperti dibawah ini, dan buat ubuntu_php7.4 baru dengan menggunakan command lxc-create

   ```markdown
    lxc-destroy ubuntu_php7.4
   ```

   ![2 1](https://user-images.githubusercontent.com/92350603/144401209-e815c339-0fd8-41a8-a343-7ec871bd0088.png)


   - Setelah membuat baru, gunakan command lxc-start untuk memulai ubuntu_7.4 dan gunakan command lxc-attach untuk membuka ubuntu_7.4. Lalu gunakan install nano untuk mengedit config.

     ![2 2](https://user-images.githubusercontent.com/92350603/144401633-87337fe6-2330-4b78-b2c6-aba54872865c.png)

     
   
   - Atur IP ubuntu_php7.4
   
     Dengan Menggunakan

     ```markdown
     sudo lxc-start -n ubuntu_php7.4
     sudo lxc-attach  -n ubuntu_php7.4
     nano /etc/netplan/10-lxc.yaml
     netplan apply
     
     ```

    ![2 3](https://user-images.githubusercontent.com/92350603/144401820-d4254d7e-7214-4d9c-afcf-1523f8288f90.png)

    ![2 4](https://user-images.githubusercontent.com/92350603/144401841-0ab16777-12c0-46b4-94de-3edf69834578.png)

   
   - Hentikan ubuntu_php7.4 dengan menggunakan command dan auto start

     ```markdown
     lxc-stop ubuntu_php7.4
     ```

     ![2 5](https://user-images.githubusercontent.com/92350603/144402034-6889633f-5735-4637-b510-904f71223323.png)
 

   - Cek lxc dengan menggunakan 

   ```
    lxc-ls -f
   ```
   
   - install ssh
   
      ![2 6](https://user-images.githubusercontent.com/92350603/144402143-ff6b1bc7-c4ff-4aed-8b31-7495094a0a92.png)

      ![2 7](https://user-images.githubusercontent.com/92350603/144402153-066381a4-38e8-4aa1-b025-56457475a4c1.png)

   
   - Atur password baru
   
    
     ![2 8](https://user-images.githubusercontent.com/92350603/144402209-a2a69e6d-83cf-471e-ae27-d75b985b9762.png)

   
   - cek ssh apakah sudah berjalan atau belum
    
     <img width="325" alt="2 9" src="https://user-images.githubusercontent.com/92350603/144402245-1574b0ac-6ade-406b-935e-e2868882c826.PNG">





