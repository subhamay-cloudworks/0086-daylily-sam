# Project Daylily: A Step Function Demo using SNS (Simple Notification Service) and Wait state.

This is a simple demo of an AWS Step function using SNS (Simple Notification Service) and Wait state.

## Description

This sample project creates a step function with a task timer. It implements an AWS Step Functions state machine that implements a ```Wait``` state, and uses an AWS Step function task that sends an Amazon Simple Notification Service (Amazon SNS) notification. A ```Wait``` state is a state type that waits for a trigger to perform a single unit of work.

The entire stack is created using AWS SAM (Serverless Application Model).

![Project Daylily - Design Diagram](https://subhamay-projects-repository-us-east-1.s3.amazonaws.com/0086-daylily/daylily-architecture-diagram.png?)

![Project Daylily - Services Used](https://subhamay-projects-repository-us-east-1.s3.amazonaws.com/0086-daylily/daylily-services-used-sam.png?)

![Project Daylily - Workflow](https://subhamay-projects-repository-us-east-1.s3.amazonaws.com/0086-daylily/daylily-step-function.png?)

### Prerequisite

* Install SAM CLI by following the Developer Guide (https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html)

* Create a Customer Managed KMS Key which will be used to encrypt the SNS.


### Installing

* Clone the repository https://github.com/subhamay-cloudworks/0086-daylily-sam 
* Create a S3 bucket to store the code repository.
* Create the folders - daylily/cft/nested-stacks
* Upload the following YAML templates to daylily/cft/nested-stacks
    * sns-stack.yaml
    * iam-role-stack.yaml

* Run the following SAM CLI Commands and pass the required parameters:

```
sam build

sam deploy --guided --capabilities "CAPABILITY_NAMED_IAM"
```

* To delete the stack, either delete it from AWS CloudFormation Console or using CLI Command:
```
aws cloudformation delete-stack --stack-name <Name of the stack> --region <Region>
```



### Executing program

* Go to the Step Function Console and use the sample input and start the execution
```
{
    "waitSeconds": 10,
    "Message": "Testing Step Function - Task Timer and SNS"
}
```

## Help

Post message in my blog (https://blog.subhamay.com)

## Authors

Contributors names and contact info

Subhamay Bhattacharyya  - [subhamay.aws@gmail.com](https://blog.subhamay.com)

## Reference
https://docs.aws.amazon.com/step-functions/latest/dg/sample-project-transfer-data-sqs.html

## Version History

* 0.1
    * Initial Release

## License

None

## Acknowledgments
[AWS] (https://docs.aws.amazon.com/step-functions/latest/dg/task-timer-sample.html)

