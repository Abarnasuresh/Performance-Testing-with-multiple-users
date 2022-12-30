## Vendor Portal(Performance Testing) Multiple users with multiple po 
### 1.Performance Testing
Performance Testing is the process of analysing the quality and capability of the product, in this method we can see the system performance in speed, stability under varying workload. 
### 2.Thread Group 
The Recorded Script we have to open the jmx file into the Apache J meter 
#### Note: Record the script with help of Blaze meter 
![thread](https://user-images.githubusercontent.com/88279523/210039036-c727a5fe-a301-4705-b6ca-981263fa6c9e.png)
#### Note: In the Thread group I have given the multiple users as 10 and    should set the ramp up seconds – the times that takes to login one by one users  
### 3.J-meter (Sidebar)
![thread (1)](https://user-images.githubusercontent.com/88279523/210039059-f892cc84-d1e1-4e4c-b5fc-ad4f5aca5893.png)
Thread group holds the controllers, samplers, config elements also the listeners 

Under the Thread Group we can find the  
* Transaction Controller – Used to group multiple sampler request into one. 
### 4.Login Request 
![email](https://user-images.githubusercontent.com/88279523/210039207-8ea0093c-3e20-4f5e-8bb6-32e61ddc0acc.png)
In the Login API we used ”post”, the body data as email and password which as variable.
### 5.Regular Expression Extractor 
![rr](https://user-images.githubusercontent.com/88279523/210039250-a4e9436e-45d0-4ed5-841f-a364e0fa51c6.png)
It is post processor that can be used to apply regex on response data. 

In the Login Http request we have to add ==> Post processors==> Regular Expression Extractor 
Inside the login API in the field of response header we will set as: 
* Name of the variable: we can set any variable name in the given field BearerToken 
* Regular expression: authorization: (.*) 
* Template: $1$  
* Match No: 0 If we give 0 the random values will be taken 
* Default value: Not found 
