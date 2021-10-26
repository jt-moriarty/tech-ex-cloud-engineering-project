A repo for demonstrating Team 5's Tech Ex Cloud Engineering Project: 

A CI/CD pipeline (built with AWS CodePipeline) for deploying an AWS CloudFormation stack from a template file hosted in this GitHub repository. 
This pipeline uses AWS CodeBuild to integrate with the third-party tool Bridgecrew, 
which performs automated security checks against our CloudFormation template files, 
displaying the results of those tests in the AWS console. 
The pipeline proceeds with the automated deployment of the CloudFormation stack if those security checks are passed.

The buildspec.yaml file is used as the Buildspec of the AWS CodeBuild Build Project. 
The demo.yaml file contains the CloudFormation stack that we wish to test for security issues and deploy.
The pipeline.json file is the JSON export of the AWS CodePipeline, retrieved with "aws codepipeline get-pipeline --name tech-ex-project-pipeline" using the Amazon CLI.

Source URLs:

https://bridgecrew.awsworkshop.io/cloudformation.html
https://itnext.io/how-to-access-git-metadata-in-codebuild-when-using-codepipeline-codecommit-ceacf2c5c1dc
https://towardsthecloud.com/validating-cloudformation-templates-in-aws-codepipeline

TODO:

4. Add build parameters for skipping specific BridgeCrew checks or soft-failing those checks.
5. Adjust buildspec.yaml to configure bridgecrew in a way that produces less complaints from Python.
7. Have the AWS CodePipeline automatically update the buildspec for the AWS CodeBuild Build Project when a change in buildspec.yaml occurs.
8. Once non-test version of pipeline is created and confirmed working, disable old pipeline and destroy related resources.
9. Better security for AWS IAM roles for group members.
10. Add automatic remediation through Bridgecrew console to demo.