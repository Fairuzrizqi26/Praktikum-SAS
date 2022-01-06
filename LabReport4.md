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

![Screenshot (330)](https://user-images.githubusercontent.com/92350603/148335598-b7c55f38-c5ab-414a-9793-728f133c61ab.png)
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


Go back to the VM and write the script as below to add upstream landing, php5,and php7


```markdown
nano /etc/nginx/sites-available/vm.local
```
to add upstream landing, php5, and php7
  
![Screenshot (342)](https://user-images.githubusercontent.com/92350603/148335782-bfde24e3-f812-422a-8eeb-40bb5d48436a.png)
change the proxy_pass

![Screenshot (343)](https://user-images.githubusercontent.com/92350603/148335784-d8c75ae8-94bc-4ee0-b9fb-a71696502196.png)
  
Then we go back to the jmeter 
  
* 50

![Screenshot (366)](https://user-images.githubusercontent.com/92350603/148344664-c319ccdf-6c27-407b-9aeb-3e3e07b04920.png)
![Screenshot (367)](https://user-images.githubusercontent.com/92350603/148344668-1c9a3373-7f17-4a83-8416-9589d023b4a7.png)
![Screenshot (369)](https://user-images.githubusercontent.com/92350603/148343712-4110086b-8727-4063-8d82-0a140a0c12c6.png)
![Screenshot (368)](https://user-images.githubusercontent.com/92350603/148343722-12c0a3ba-7b27-4cd5-9760-ddf8058af8a8.png)

* 100
![Screenshot (362)](https://user-images.githubusercontent.com/92350603/148343766-2511c487-8312-4aaf-9422-c5ce6c01673a.png)
![Screenshot (363)](https://user-images.githubusercontent.com/92350603/148343780-57ff2dcc-1766-417d-b89d-44bba657f470.png)
![Screenshot (364)](https://user-images.githubusercontent.com/92350603/148343785-4b939366-c9c9-4bf6-9127-2aebade09a1c.png)
![Screenshot (365)](https://user-images.githubusercontent.com/92350603/148343790-73054c97-e440-4647-8b71-c0e99a2874e0.png)

* 150
![Screenshot (361)](https://user-images.githubusercontent.com/92350603/148343836-7e23a13e-decd-431d-8d84-e0215566f8b9.png)
![Screenshot (360)](https://user-images.githubusercontent.com/92350603/148343840-bbae8187-c9e1-43ac-82e0-193d3be1ff13.png)
![Screenshot (359)](https://user-images.githubusercontent.com/92350603/148343856-1f986865-a10e-4dcf-8c6b-a0398d031661.png)
![Screenshot (358)](https://user-images.githubusercontent.com/92350603/148343862-b95dc8a5-bdc0-4450-b128-4070e6d98a05.png)


### Analysis

Below is the results from when we use load balancer and not using the load balancer

 - When there is 50 users that access our web, if we don't use load balancer the average time of user accessing our web is
   - landing : 2444 ms / 2.4 s
   - blog : 2347 ms / 2.3 s
   - app : 19 ms / 0.019 s
- When we use load balancer, then
  - landing : 1841 ms / 1.8 s
   - blog : 1379 ms / 1.3 s
   - app : 12 ms / 0.012 

Here we can know that the average time of user accessing our web is faster then if we don't use load balancer. For the throughput or the amount of user accessing our web is

- When there is 50 users that access our web, if we don't use load balancer the amount of user accessing our web is

  - landing : 16 user / second
  - blog :  12 user / second
  - app : 22 user / second

- When we use load balancer, then

  - landing : 42 user / second
  - blog :  29 user / second
  - app : 30 user / second

  Here we can know that the average time of amount of user accessing our web in 1 second is faster then if we don't use load balancer.

  

  The conclusion is, if we use load balancer, then the time is faster and the amount of users that accessing our web is much more then when we don't use load balancer.
