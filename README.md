A repo for demonstrating Team 5's Tech Ex Cloud Engineering Project: 

A CI/CD pipeline (built with AWS CodePipeline) for deploying an AWS CloudFormation stack from a template file hosted in this GitHub repository. 
This pipeline uses AWS CodeBuild to integrate with the third-party tool Bridgecrew, 
which performs automated security checks against our CloudFormation template files, 
displaying the results of those tests in the AWS console. 
The pipeline proceeds with the automated deployment of the CloudFormation stack if those security checks are passed.

The buildspec.yaml file is used as the Buildspec of the AWS CodeBuild Build Project, 
and the demo.yaml file contains the CloudFormation stack that we wish to test and deploy.

Source URLs:

https://bridgecrew.awsworkshop.io/cloudformation.html
https://itnext.io/how-to-access-git-metadata-in-codebuild-when-using-codepipeline-codecommit-ceacf2c5c1dc
https://towardsthecloud.com/validating-cloudformation-templates-in-aws-codepipeline

TODO:

1. Recreate pipeline in us-east region with non-bridgecrew demo names that is hooked up to this repository.
2. Find a sufficiently complex (yet not too complex) CloudFormation template to use for the in-class / recorded demo.
3. Cut out or modify aws-code-extras script that pulls environment variables that are no longer fully working in AWS CodeBuild.
4. Add build parameters for skipping specific BridgeCrew checks or soft-failing those checks.
5. Adjust buildspec.yaml to configure bridgecrew in a way that produces less complaints from Python.
6. Adjust buildspec.yaml to work with branches that are not named "master".
7. Have the AWS CodePipeline automatically update the buildspec for the AWS CodeBuild Build Project when a change in buildspec.yaml occurs.
8. Once non-test version of pipeline is created and confirmed working, disable old pipeline and destory related resources.
9. Better security for AWS IAM roles for group members.
10. Add automatic remediation through Bridgecrew console to demo.