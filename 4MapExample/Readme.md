"Map Example" 
<pre>
{
  "Comment" : "Using Map State", 
  "StartAt" : "MapState", 
  "States" : {
    "MapState" : {
      "Type" : "Map",
      "ItemsPath" : "$.array",
      "Iterator" : {
        "StartAt" : "First",
        "States" : {
          "First" : {
            "Type" : "Pass",
            "Result" : "result1",
            "ResultPath" : "$.result",
            "Next" : "Second"
          },
          "Second" : { 
            "Type" : "Pass",
            "Result" : "result2",
            "ResultPath" : "$.result2",
            "End" : true
          }
        }
      },
      "End" : true
    }
  }
}
</pre>

![image](https://user-images.githubusercontent.com/69715143/178265384-2afbb4d2-6a91-435c-bdec-fe1bfb9d22da.png)
