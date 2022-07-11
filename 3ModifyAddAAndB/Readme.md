"3. Choice Example" 

Code : 
<pre>
{
  "Comment" : "Add or mutiply off the elements of the array if the provided op is 'add' or 'mul' respectively",
  "StartAt" : "Choice",
   "States" : {
     "Choice" : {
       "Type" : "Choice",
       "Choices" : [
         {
           "Variable" : "$.task",
           "StringEquals" : "First",
           "Next" : "First"
         },
         { 
         "Variable" : "$.task", 
         "StringEquals" : "Second",
         "Next" : "Second"}
       ],
       "Default" : "Default"
     },
     "First" : { 
      "Type" : "Pass",
       "Result" : "This is first Task",
      "End" : true 
     },
     "Second" : { 
     "Type" : "Pass",
     "Result" : "This is second Task",
       "End" : true
     },
     "Default" : {
       "Type" : "Pass",
       "Result" : "This is default Task",
       "End" : true
     }
   }
}
</pre>

![image](https://user-images.githubusercontent.com/69715143/178256505-0774808c-61a3-471e-bd6c-0359298194d1.png)
