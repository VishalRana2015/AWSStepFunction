"Wait Example" 
<pre>{
  "Comment" : "Wait Example",
  "StartAt" : "WaitState",
  "States" : {
    "WaitState" : {
      "Type" : "Wait",
      "Seconds" : 10,
      "Next" : "Second"
    },
    "Second" : {
      "Type" : "Pass",
      "Result" : "Passed",
      "ResultPath" : "$.result",
       "Next" : "SucceedState"
    },
    "SucceedState" : {
      "Type" : "Succeed"
    }
  }
}
</pre>

![image](https://user-images.githubusercontent.com/69715143/178266168-bc8a7d9d-8022-4c71-a74e-aa7604860931.png)
