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

If the input contains "First" as a value for "task" field of the input, then "First" task will be invoked. Similarly if the input contains "Second" as the value of "task" field then "Second" task will be invoked. If the input contains any other value for the "task" field" then the Defualt task will be invoked.
Exmaple: 
<pre>
{ 
"task" : "First" 
}
</pre>

But what happens if the input does not contain "task" field at all. 
The execution gets failed.
To invoke the default Task even if the input does not contain "task" field in it. update the Workflow with code given below.
<pre>
{
  "Comment" : "Add or mutiply off the elements of the array if the provided op is 'add' or 'mul' respectively",
  "StartAt" : "Choice",
   "States" : {
     "Choice" : {
       "Type" : "Choice",
       "Choices" : [
         {
           "And" : [
             {
               "Variable" : "$.task",
               "IsPresent" : true
             },
             {
               "Variable" : "$.task",
               "StringEquals" : "First"
             }
           ],
           "Next" : "First"
         },
         { 
         "And" : [
           {
             "Variable" : "$.task",
             "IsPresent" : true
           },
           {
             "Variable" : "$.task",
             "StringEquals" : "Second"
           }
         ],
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
