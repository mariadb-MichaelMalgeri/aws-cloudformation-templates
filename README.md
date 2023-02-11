# aws-cloudformation-templates (CFT)

These templates leverages  AWS Systems Manager/Parameter store

In order to run the aws CLI commands to launch the CFT you will probably need to set the following environment variables:

Here they are set in a .bash_profile file

export AWS_DEFAULT_REGION=xxx  

export AWS_ACCESS_KEY_ID="xxxx"  

export AWS_SECRET_ACCESS_KEY="xxx"  

export AWS_SESSION_TOKEN='xxx'   



# xpand-cluster-ebs.yaml

**This CFT will create a 3-node Xpand cluster in the virtual private cloud specified by the VpcID 
The cluster will be front-ended with a MaxScale instance**

The following parameters should be set in the AWS Systems Manager/Parameter store for this template

VpcID
ImageIDXpand
MyIp
xpandLicenseCompany
xpandLicenseEmail
xpandLicensePerson
xpandLicenseSignature
xpandLicenseExpiration
xpandPassword
xpandToken
xpandVersion
xpandVersionDir

Run the template to create the cluslter with the following commands

\# cd to_project_directory
\# aws cloudformation create-stack --stack-name your_stack_name --template-body file://xpand-cluster-ebs.yaml

To configure the MaxScale GUI, see page 27 of the MariaDB MaxScale Lab Exercises or following the instructions at this URL
https://mariadb.com/resources/blog/getting-started-with-the-mariadb-maxscale-gui/

To delete a stack created with this CFT run the following commands

\# cd to_project_dir
\# aws cloudformation delete-stack --stack-name your_stack_name