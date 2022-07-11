"Add A and B" 

Code: 
<pre>
{
  "Comment": "A Hello World example of the Amazon States Language using Pass states",
  "StartAt": "Lambda Invoke",
  "States": {
    "Lambda Invoke": {
      "Type": "Task",
      "Resource": "arn:aws:states:::lambda:invoke",
      "OutputPath": "$.Payload",
      "Parameters": {
        "FunctionName": "arn:aws:lambda:ap-south-1:637888367425:function:AddAAndB:$LATEST",
        "Payload.$": "$"
      },
      "Retry": [
        {
          "ErrorEquals": [
            "Lambda.ServiceException",
            "Lambda.AWSLambdaException",
            "Lambda.SdkClientException"
          ],
          "IntervalSeconds": 2,
          "MaxAttempts": 6,
          "BackoffRate": 2
        }
      ],
      "End": true
    }
  }
}
</pre>

![image](https://user-images.githubusercontent.com/69715143/178252193-bab23ce7-ed7f-46dd-8a8a-cd092fce3853.png)
Whenever you invoke Lambda function you need to provide <b>FunctionName</b> filed and <b>Payload</b> field in the input. You can see the Workflow visual editor has configured this using Parameters.
