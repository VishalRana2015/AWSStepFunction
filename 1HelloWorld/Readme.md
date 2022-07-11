"Hello World Step Function" 
![image](https://user-images.githubusercontent.com/69715143/178248435-f2005787-d3bb-41c0-9cfd-bbb3d19e9646.png)

Code: 
<pre>{ 
"Comment" : "My First hello funciton",
  "StartAt" : "printHelloWorld", 
  "States" : {
    "printHelloWorld" : {
    "Type" : "Pass",
    "Result" : "Hello world!!!",
    "End" : true
    }
  }
}
</pre>
