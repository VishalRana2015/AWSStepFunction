"Parallel State Example" 

<pre>
{
  "Comment" : "Parallel State Example", 
  "StartAt" : "ParallelState",
  "States" : {
    "ParallelState" : {
      "Type" : "Parallel",
      "Branches" : [
        {
          "StartAt" : "First",
          "States" : {
            "First" : {
              "Type" : "Pass",
              "Result" : "First State Result",
              "ResultPath" : "$.first",
              "End" : true
            }
          }
        },
        {
          "StartAt" : "Second",
          "States" : {
            "Second" : {
              "Type" : "Pass",
              "Result" : "Second State Result",
              "ResultPath" : "$.second",
              "End" : true
            }
          }
        }
      ],
      "End" : true
    }
  }
}
</pre>

![image](https://user-images.githubusercontent.com/69715143/178267645-36be3d33-b8bd-4417-bb3a-4e5f0e28fe3a.png)

Output to following input: 
<pre>
{ "comment" : "Insert your JSON here" }
</pre> <br/>
<pre>
[
  {
    "Comment": "Insert your JSON here",
    "first": "First State Result"
  },
  {
    "Comment": "Insert your JSON here",
    "second": "Second State Result"
  }
]
</pre>
