# **Modul 4 Practicum Report**

### By : Fairuzrizqi Nugraharsanto  &  Budhi Priambodo

* First, make 2 copies of containers, and then start

![Screenshot (323)](https://user-images.githubusercontent.com/92350603/148335067-b8f6db73-4f00-494b-9f5e-e45c0b3ee66e.png)

![Screenshot (324)](https://user-images.githubusercontent.com/92350603/148335063-f84e4651-242b-4a69-b0ee-32bab0cc0649.png)


* Next, open ubuntu_php7.4_2 and change the IP address to 10.0.3.111/24. Do the same thing on ubuntu_php7.4_3, change the IP address to 10.0.3.121

![Screenshot (325)](https://user-images.githubusercontent.com/92350603/148335112-d51ac500-d1ad-4855-b9bd-b5d3e4ce38c4.png)


* Go to lxc_php7_2.dev and change the server name

![Screenshot (326)](https://user-images.githubusercontent.com/92350603/148335194-27de4b59-1893-477d-924b-90e551b8c3e0.png)
![Screenshot (327)](https://user-images.githubusercontent.com/92350603/148335199-eb878f2e-669d-4f61-9dcc-f82fe5c44a3a.png)

* Restart nginx and curl it. 

  
![Screenshot (328)](https://user-images.githubusercontent.com/92350603/148335221-de35f964-ab1e-4797-8cbf-281b5c685a39.png)

* Next step is ubuntu_php7.4_3 (IP 10.0.3.121), debian_php5.6_2 (IP 10.0.3.112), debian_php5.6_3 (IP 10.0.3.122) the same as ubuntu_php7.4_2.
* Add name server /etc/hosts (on VM)

![Screenshot (329)](https://user-images.githubusercontent.com/92350603/148335281-a76f6963-a2e9-414f-9d8c-076642cc0273.png)


* Run the jmeter, and change the number of threads

![Screenshot (331)](https://user-images.githubusercontent.com/92350603/148335539-3dbca5bb-48a5-4362-85e4-27d92e283621.png)
![Screenshot (332)](https://user-images.githubusercontent.com/92350603/148335541-8f5ffe4e-acf3-43e0-b87e-1757c56a4f1d.png)
![Screenshot (333)](https://user-images.githubusercontent.com/92350603/148335546-08d752f1-c736-4ca1-b926-1d661bc7baa4.png)
![Screenshot (334)](https://user-images.githubusercontent.com/92350603/148335550-2cc950d7-8b4a-4098-8082-57295542bc2e.png)
![Screenshot (335)](https://user-images.githubusercontent.com/92350603/148335556-91c0282a-c82e-42ad-9ebb-10e8d13d5d81.png)
![Screenshot (336)](https://user-images.githubusercontent.com/92350603/148335561-df8c0f9c-b6ed-4af5-b3e5-d7bc5369cbb9.png)
![Screenshot (337)](https://user-images.githubusercontent.com/92350603/148335565-2f48e694-6093-440c-8741-eebd3b9095fb.png)
![Screenshot (338)](https://user-images.githubusercontent.com/92350603/148335572-a08d355d-ad20-4293-a256-c1d0328bdb9a.png)
![Screenshot (339)](https://user-images.githubusercontent.com/92350603/148335578-ec1f8894-c519-49a0-a940-a7dc4d09f85f.png)
![Screenshot (340)](https://user-images.githubusercontent.com/92350603/148335584-8c4f397a-73b4-420d-85f2-1fd152a62010.png)
![Screenshot (341)](https://user-images.githubusercontent.com/92350603/148335592-c92c77a8-a076-49da-be8a-aa9679e7749e.png)
![Screenshot (330)](https://user-images.githubusercontent.com/92350603/148335598-b7c55f38-c5ab-414a-9793-728f133c61ab.png)




* Go back to the VM and write the script as below to add upstream landing, php5,and php7


```markdown
nano /etc/nginx/sites-available/vm.local
```

![Screenshot (342)](https://user-images.githubusercontent.com/92350603/148335782-bfde24e3-f812-422a-8eeb-40bb5d48436a.png)
![Screenshot (343)](https://user-images.githubusercontent.com/92350603/148335784-d8c75ae8-94bc-4ee0-b9fb-a71696502196.png)

///////


//////

![Screenshot (350)](https://user-images.githubusercontent.com/92350603/148336199-13d5cd3d-74bd-4322-87ea-708d594be2e0.png)
![Screenshot (351)](https://user-images.githubusercontent.com/92350603/148336202-1708ed6e-870c-494f-903f-e37ae48fd15e.png)
![Screenshot (352)](https://user-images.githubusercontent.com/92350603/148336203-7dd06c8c-b6f3-44f0-99f5-9b5274563fd1.png)
![Screenshot (353)](https://user-images.githubusercontent.com/92350603/148336205-13534adc-d6e9-4668-bbe6-15f757bedd55.png)
![Screenshot (354)](https://user-images.githubusercontent.com/92350603/148336207-76e50ab8-5c3a-49f3-8092-e48c6ac09610.png)
![Screenshot (355)](https://user-images.githubusercontent.com/92350603/148336209-36059e20-ab25-4af4-b132-d192c25b9875.png)
![Screenshot (344)](https://user-images.githubusercontent.com/92350603/148336212-c78dc880-4849-4e14-b16b-a9e2d275952c.png)
![Screenshot (345)](https://user-images.githubusercontent.com/92350603/148336214-9186e932-d283-4a38-b0c8-5bcace2b4750.png)
![Screenshot (346)](https://user-images.githubusercontent.com/92350603/148336215-65587d42-320c-4d57-be4f-d38a10443dc5.png)
![Screenshot (347)](https://user-images.githubusercontent.com/92350603/148336219-237c3da6-dfe0-427c-986d-8f2a4d63595c.png)
![Screenshot (348)](https://user-images.githubusercontent.com/92350603/148336223-5094e48d-8861-4c57-af36-ec92ca922625.png)
![Screenshot (349)](https://user-images.githubusercontent.com/92350603/148336225-a40668a4-c3fd-4c5e-a3ac-8a37bfd42d98.png)


### Analysis
