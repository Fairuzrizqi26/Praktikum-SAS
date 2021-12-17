# **Module 3 LabReport**

## **By : Fairuzrizqi Nugraharsanto & Budhi Priambodo**

### **Study Case**

Create SubDomain dev.vm.local with rules :

* Ansible
* Same lxc like vm.local
* The folder must be in var/www/html/dev{name_app}



### **Problem Solving**

* The first step is to go to the directory using ansible
![1](https://user-images.githubusercontent.com/92350603/146415140-495139c7-9b63-4310-9c56-03ea95afcee4.png)


  ```
  ---
  - hosts: all
    become : yes
    tasks:
      - name: install bind9 dan dnsutils
        apt:
         pkg:
           - bind9
           - dnsutils
  ```
  ![2](https://user-images.githubusercontent.com/92350603/146415273-a21d1f4d-3f51-4b16-9767-f370a064208f.png)


* The next step is install packages with ansible

 ![3](https://user-images.githubusercontent.com/92350603/146415223-e119bf3a-509c-4d19-8245-5f3cffaa062f.png)


* Create e config.yml file

 ![4](https://user-images.githubusercontent.com/92350603/146415401-17515268-6d33-4031-8951-115ba54fd6e6.png)

 ![5](https://user-images.githubusercontent.com/92350603/146421722-8a51d026-e671-4c24-8c25-9afdd40d457a.png)

  ```
  ---
  - hosts: all
    become : yes
    tasks:
     - name: membuat direktori
       file:
        path: /var/www/html/dev/landing
        state: directory
     - name: copy file vm.local
       copy:
        src: /etc/bind/vm/vm.local
        dest: /var/www/html/dev/landing
     - name: mengganti konfigurasi
       replace:
        path: /var/www/html/dev/landing/vm.local
        regexp: 'www'
        replace: 'dev'
     - name: copy file named.conf.local
       copy:
        src: /etc/bind/named.conf.local
        dest: /etc/bind/named.conf.local
     - name: mengganti konfigurasi conf local
       replace:
        path: /etc/bind/named.conf.local
        regexp: '/etc/bind/vm/vm.local'
        replace: '/var/www/html/dev/landing/vm.local'
     - name: mengganti konfigurasi conf local part2
       replace:
        path: /etc/bind/named.conf.local
        regexp: '/etc/bind/vm/1.168.192.in-addr.arpa'
        replace: '/var/www/html/dev/landing/1.168.192.in-addr.arpa'
     - name: copy file 1.168.192.in-addr.arpa
       copy:
        src: /etc/bind/vm/1.168.192.in-addr.arpa
        dest: /var/www/html/dev/landing
     - name: copy file resolv.conf
       copy:
        src: /etc/resolv.conf
        dest: /etc/resolv.conf
     - name: copy file named.conf.options
       copy:
        src: /etc/bind/named.conf.options
        dest: /etc/bind/named.conf.options
     - name: restart nginx
       service:
        name: nginx
        state: restarted
     - name: restart bind9
       action: service name=bind9 state=restarted
  ```

* Do the installation using the script below

  ![6](https://user-images.githubusercontent.com/92350603/146415589-e7dfd6f2-b746-466e-b7fc-d971d3dffefa.png)

  
* Add subdomain to /etc/hosts

 ![7](https://user-images.githubusercontent.com/92350603/146421586-81af8d8c-fb2d-4a62-84d3-2e78cabae05a.png)
 ![8](https://user-images.githubusercontent.com/92350603/146421769-c7d37948-2cda-456d-9eb1-c5d0b67d7cf3.png)

* Open vm.local file

 ![9](https://user-images.githubusercontent.com/92350603/146421787-bb2a3786-2fe3-445c-b8f2-fe70a0ce6714.png)


* Add line www. After that exit lxc

  ![10](https://user-images.githubusercontent.com/92350603/146421825-89138cfd-18fc-4c24-981b-160aa8c921e2.png)
 

* Open and edit vm.local in directory /etc/nginx/sites-enabled/

 <img width="450" alt="new 1 0" src="https://user-images.githubusercontent.com/92350603/146472376-3847f9eb-0354-423e-ac38-f9819fefd120.PNG">
 
 <img width="458" alt="new 1" src="https://user-images.githubusercontent.com/92350603/146472394-5336cb19-dc58-4ec8-b96b-9b0a00c8d20f.PNG">

* Open and edit vm.local in directory /etc/bind/vm/

  <img width="479" alt="new 2" src="https://user-images.githubusercontent.com/92350603/146472518-9758c843-0464-45eb-bb59-7b7680923c3e.PNG">


* Restart all packages

  <img width="471" alt="new 3" src="https://user-images.githubusercontent.com/92350603/146472526-19410b86-4e78-4919-b799-0a66db00fde0.PNG">

- Open Wifi Settings (in the case we use linux os), add dns server and uncheck automatic at menu Ipv4
 
 <img width="332" alt="ne4" src="https://user-images.githubusercontent.com/92350603/146472677-e3ee1f98-04c5-4499-ae67-3d755bd97845.PNG">

- At menu IPv6, unchecklist

- Just reconnecting the wifi, and check dev.vm.local on the browser :)

  <img width="960" alt="new4" src="https://user-images.githubusercontent.com/92350603/146472819-50ce398e-82d2-4462-a701-581ea7d63d46.PNG">
  
  <img width="956" alt="new5" src="https://user-images.githubusercontent.com/92350603/146472825-969639c6-4a55-49f8-adae-e560e0a7be2d.PNG">



