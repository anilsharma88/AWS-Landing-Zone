# AWS Landing Zone
AWS Landig zoren is the soluation that help the customer more quickly set up a secure, multi - account AWS Envirnoment based on AWS best practices.
## Account Vending Machine(AVM)
adding new account and & baseline policy & nodify landing zone for baseline policy
- implement an initial security baseline through the creation of core account and resources
- It also provide a baseline architecute, identy and access managment, goverence, data security, network designe and logging
- additional AWS account can be provisioned with same set of security baseline in place

## Need of Landing zone
- setup best practics AWS oenvirnoment in few click
- standardize account provisioning
- centrilize policy mangement 
- enforce goverence and complience proactively 
- enable end user self- service
- get continous visibility in your AWS envirnoment
- Complience &  in differnet Envirnoment
- Setting baseline security in every account 
- centerlized mangement
- 
- increase the blast redies if account is get comprimised 
- deffecult to track the resources


## SetUp multiple AWS Envirnoment
- AWS control Tower 
- AWS organization
- AWS service Catalog
- Establish Cost control
    - AWS budgets
    - AWS Lincence Manger
    - AWS marketplace (Private MarketPlace)
- Monitor/manage Policy and security configuration
    - AWS CloudTrail
    - AWS config
    - AWS SecurityHub
    - Amazone cloud Watch
- Improve over time - operate and optimization
- AWS well architecute Tool
### Posible Way to create Landing Zone
1. Service based landing zone using AWS control tower
2. A cloudFormation soluation build AWS Landing ZOne
3. Customize landing zone you build

AWS created control tower to help you save time bu automating the setup of a landing zone so you can run secure and scalable workloads. Control Tower is manged by AWS and uses best practices and guidline to help you create your foundation envirnoment. Control Tower uses integrated services like AWS catalogs & AWS organization to provision account in your landing zone to manage access to those account.
### Image Link

## AWS Control Tower
Its a AWs service to setup landing zone quickly, AWS control tower provide easiest way to setup and govern a secure, complicence, multiaccount AWS envirnoment based on best practices established by with thousand of enterprieses. end user can provision AWS account quickly 
- control tower use integration service like AWS service catalog, and AWS organization to provisions account in your AWS Landig zone and mange access to those account
### AWS control Tower Resources
1. 2 OU 1 shared account 1 that will provision by your user 
2. 3 shared accont 
    - master, & isolated 
    - log archive
    security
3. A Native cloud directory & preconfigured group and Single sign on
4. 20 periventive Gardtrail to enfore policy & 2 detective gardtrail to detect config voilation

## Feature of Gardtrail
1. Landing zone 
    - A landig zone is well architected, multi-account AWS envirnoment that based on security and complience best practices. This is entriprise wide container that holds all of your OU, accounts, user and other resources that you want to be subject to complience regulation
    - A landing zone can scal to fit the needs of an entriprise of any size

2. Gaurdtrail
    - A Gaurdtrail is high-level rule that provides ongoing goverence for your overall AWS envirnoment . Its expressed in plain langauge
    Two kind of gardtrail exist
    1. Perventive (Source Control Policy)
    2. Detective (AWS Config)
    - Three categories of guidance apply to the two kinds of gaurdtrail
    1. Mandatory (eg. diable public access to log archive)
    2. Strong recommeded (eg disallow interent to RDP)
    3. Elective (YES/NO ) if you don't want

3. Account Factory 
    - account Factory is a configurable templet that helps to standardize the provisiong a new account with pre-approved account configuration AWS control tower after a build in account factory that helps the account provisioning workflow in your organization.

4. Dashbord
    - the dashbord offers continous oversight of your landig zone to your team of centeral cloud Admininstrator use the dashboard to see provisioned account accross your entriprise, gaurdtrail enabled for policy enforcement 
    - gaurdtrail enabled for continous detection of policy non - conformance and non-compliant resources organized by account and OUs
# Why to use Control Tower
- setup best practics AWS oenvirnoment in few click
- standardize account provisioning
- centrilize policy mangement 
- enforce goverence and complience proactively 
- enable end user self- service
- get continous visibility in your AWS envirnoment
Enable Goverence
    - setup an AWS landing zone
    - centeralize idenity & account management
    - Establish gaurdtrail for goverence 
    - automate compliant account provisioning

### Automate compliant Account  provisioning (Account Factory)
 - buid in account factory provides a template to standardize network setting( eg subnet, ip addtess)
 - Configurable network setting( eg. subnet, IP address)
 - Automate enforcement of account baseline and gaurdrails
 - publish to AWS service catalog

 ============================================================================================================
 https://www.udemy.com/course/aws-secure-landing-zone-with-control-tower-and-aft
## Core OU AWS Account
1. Network Account
    - Tranist Gateway  - is a network trasit hub that you can use to interconnet your virtual private cloud and on premis networks
        - is a network transit hub
        - is global expanded service
        - You can attach the following 
	        1. One or more vpc
        	2. peering connection with othe TGW
	        3. Direct connect Gateway 
	        4. VPN connection
        - can dynamically propagate routes
        - data is automatically encrypted 
        - data never travels over the public internet
    - IngressEgress VPC
        - Single Egress endpoint
            - high avilability, using multiple NAT gateways on different availability zone
	    - security: using the security groups , ACL's and blackhole routes
	    - scalability: natively supported by NAT 
	      - up to 55k connections to each unique destination
		  - From 5 to 45 Gbps
        - Single Ingress endpoint 
	       - less price because of no additional traffic routes
		   - less network hopes to application
    - Bastion Host: is a special-purpose compute on a network specically designed and configured to withstand attackes
              - the bridge host between the world and internal services
			  - controll command line remote login
	
    - Insepction VPN (Gateway Loadblancer) 
        - is type of loadblancer which helps to deploy, scal and manage virtusl appliances, such as firewalls, intrusion detection and prevention system and deep packet inspection system ( paloalto cisco fortinet heshicorp firewall)
        - operates at the 3rd level OSI model (network)
        - exchange application traffic using the GENEVE protocal 6081
        - MAX tranmission unit (MTU) size of 8500 bytes
        - exchange traffic across VPC using the Gateway Load
        - route are working based on route table
   

2. Shared service account
    - is the centrilize HUb for most of common service used in AWS account
    - shared configured :- storing the shared configuration used by different applications/services (S3 Bucked, DynoDb Table)
    - CICD Processes -  storing the shared configuration used by different application/services (storing artifict ecr etc)
    - Active directory - [AMS - Managd Actived Directory] Is utilized for user/resource management, authentication/authorization and DNS, accross all of your AMS multi-account landing zone accounts.
    - AWSmarketplace : enable qualified partner to market and sell their software to aws coustomers.
    - AWS License Manger service: Makes it easier for you to manage your software venders cenrrally accross AWS and your on-premises envirnoment.
    - CloudTrail 
    -  config
    -  cloudwatch
    -  VPCFlowlog


3. Security Account :
    -  the security account is the central hub ford housing security-related operations and for funneling notifications and alerts
    - AWS COnfig: is a service that enables you to assess, audit and evalute the configurations of your AWS resources
        **Detalis :** 
        - determination of configuration for AWS resouces
        - continuously monitoring and recording of AWS resouce configuration
        - automated evaluation of recoreded configurations against desired configuration
        - integrations with other AWS services
 
    - AWS Inspector: - is an automated vulnerability managment service that .continually scans Amazon EC2 and and container workloads for software vulnerabilityand unintended network exposure.
		**Assessment Setups:**
	    - Network Assessment : Network analysis of Ec2 instances on VPC and outside(Ports reachability etc.)
		- Host Assessment: software vulnerable(CVE) hosts handening (CIS) and security best practices

		- enable trust relation between managment account 
		- service-linked role permissions:
		     - Enable or disable scans for member accounts 
			 - view aggregated finding data from the entire organization
			 - create and manage suppression rules
			 
    - Security Hub: - is a cloud security posture management service that performs security best practice checks aggregates alerts and enables automated remediation
			   
	    **Detalis:** 
	    - aggregate finding from various services 
	    - gaurduty, inspectr ,config coudtrail etc.
		- auromate remidition finding
		- privide centrilized reporting
		
	    - SNS - Notification 

4. Log Archive Account : 
    - The log archive account serves as the central hub for archiving logs across your AMS multi-account landing zone envirnoment and consist inside the S3 buckets with copies of your recoreds and reports from AWS services					
	- you could use this account for your centralised logging solution with AWS Firehose or splunk and any other logginf tools 
	- access should be limited to a restricted list of auditors and security team.		
	- Security Reports: - store reports and finding from the security services
	- VPC Flow Logs: store network activity logs
	- CloudTrail record contents : -store account activity records
	- application logs: - store history of application logs
		-- configure s3 bucket policy 
		--  configure IAM policy 
		-- enable versioning for critical data
		-- configure s3 lifecycle policys
		-- store the data to archive

5. Workload account
```
master 
     core OU 
		- Network account
		- shared service account
		- logarchive account
		- security account
	apps OU - 
	  prod
	  pre-prod
	sendbox OU
	  - sendbox account
```
Operation tasks access
- incident managment
- security management
- backup managment 
- costs otimization management 
- Monitoring
- event

## Type of application account
1. AMS - managed application account : are application account that are fully managed by AWS
2. Developer mode application accounts (AMS+)
     - are application acconts to provision and update AWS resources outside of the AMS change management process 
3. Customer managed AWS account:
    - are application accounts with full control to self-operate the infrastructure
4. Sandbox Accounts: 
   - are free from policies accounts to perform integration development or testing envirnoment.
      Sandbox policy 
	   - isolation 
	     account should be isolated from any kind to connection
	  - data classification 
	    account should not store any coustomer data
	- Access control
	   account should have strict policies
	Tagging Policy
	-  account should have only tagged resources
	Resource Lifecycle
	 - account should have a control mechanism of resources 
    
Impelamenation WAY 

1 AWS Organization + AWS Controll Tower Account factory for terraform

 Pros:
  - Landing Zone
    - one maintain point
    - possible to limit account permissions
    - Consolidation billing possibility
    - AWS best practices follow up 
    - Automation of account maintaing
   - Infrastructure as code supported
Cons: 
 Required experience in maintaing
** Terraform module that makes it easy to create and customize new accounts that maintain with your organinzstion security guidances 

   
1. Aws organizations + AWS controlTower
	- enables you to enforce and manage governance rules for security, operations and compliance at scale across all your organizations and account
Pros: 
    Landig zone
	possible to limit account permissions 
	consolidation billing possible
	aws best practices follow up
	automation of account maintaning
cons: No ifrastructure as code
      Required experience in maintaining
	  
2. AWS Organizations 
    allow you programmatically manage AWS accounts and organize them.
	
	Pros: 
	possible to limit account permissions 
	consolidation billing possible
	aws best practices follow up
	automation of account maintaning
cons: No ifrastructure as code
      Required experience in maintaining

###  Securing of master Account
- setup root password
- Enable MFA on root user 
- Prepare password policy
- creation of the user
- prepare building notifications
  KMS key
  SNS topic 
  Budget alerts

# AWS COntrol Tower
Is a service that enables you to enforce and manage fovernance rules for security, operations, and compliance at scale across all your organizatins in the AWS CloudTrail
- automate process of provisioning of accounts 
- apply guardrails for ongoing governance
- automate setup of landing zone best practice

 Default setup 
2 OU ( Security , sandbox)
2 account in security ou ( log archive, Audit)

AWS Service Catalog : 
	- is a service allows organizations to create and manage catalogs of IT services
- create or enroll an accounts 
- update and move accounts
- close accounts
- resouce considerations for accounts 
    - AWS cloudFormation stacks
	- AWS cloudWatch Event Rules and Logs
	- AWS IAM Roles and Policies
	- AWS Lambda Functions
    - AWS SNS topics	

# Service Control Policies
 FullAWSAccess
 - AWS Managed policy
 - not editable
 - allows access to any operations
 - attache to each account by default
AWS IAM 
 IAM Policy
 IAM Roles
 SSO Permission sets
 SSO Users
 Default 
   AWSControlTowerExecution
   aws-controltower-ReadOnlyExecutionRole
   

# Audit Account
 Config rules
 SecurityHub dashboard
 SNS notification topics
 
 AWS CloudTrail
 Organization Trail: - trail that logs all events for all AWS acconts in  organization.
 - multi-region trail
 - multi-account trail
 - trail visible on member accounts
 - trail is not editable on member accounts
 - all cross accounts logging tasks done by AWS managed role
 
 IAM Access Analyzer
  - Iam access analyzer uses provable security to analyze all access paths and provide comprehensive analysis of ecternal access to your resources.
  
  Analysis of services
	- AWS IAM policies
	- Lambda permissions
	- AWS s3 bucket policies
	- SQS queuses permisions
	- KMS key policies
	Properties
		- can reacts on findings
		- can alalyze the organization
AWS Security HUB 
    - AWS Security Hub is a cloud security posture management service that performs security best practices check, aggregates alerts, and enables automated remediation
	   - centralized security dashboard
	   - findings analysis using AI and prioritization system
	   - React on findings
	   
	  Collect security data from 
	  - AWS security services
		- AWS lnspector 
		- AWS GaurdDuty
		- AWS macie
		- AWs firewall
		- AWS access Analyzer
	Supported third - party partner products
	AWS accounts on organization
	
	Deligated administrator to security account
AWS GaurdDuty
   - is a threat detection service that continuously monitors your AWS accounts and workloads for malicious activity and delivers detailed security findings for visibility and remediation.
   
   Monitored Services:
	- Route53 DNS query logs
	- CloudTrail events
	- VPC flow logs
	
  Properties:
	- Real-time minitoring
	- Reaction on findings
	- Support organization delegated administration
Deligated administrator to security account

Amazone Inspector
 - is an automated vulnerability managment service that continually scan AWS workloads for software vulnerabilitys and unintended network exposure.
 Assessment setups (types of checks):
  - Network Assessment
  - Host Assessment
 Properties:
 - Network accessibility verificatin
 - Verfication of security vulnerabilitys
 - Automated reaction on findings
 - support of delegated administrator feature
 
 
OverView (IMportant)
AWS control Tower Account Factory for Terraform(AFT)
 - is a terraform module that makes it easy to create and customize new accounts that comply with your orginazation's security guidelines
 AFT architecure has three high-level principles:
	AFT Pipeline(mandtory)
	- is amin automated pipeline for accounts creation and cutomization
	AFT Feature Options(Optional)
	- are build-in components
	- cloudTrail data event logging to s3
	- Removing default VPC in all regions
	- Automated enrollment in AWS
	  Enterprise Support plan 
	AFT Customizatin (Optional)
	- customization scripts implementation
	 ( Terraform and others)
	 

1. AFT account creation procedure 
    1. Define TF script with account information and push on GIT changes
	2. CodeStar receive notification about changes and trigger codeBuild with the implementation of TF script
	3. CodeBuild insert DynamoDB item with new account request
	4. DynamoDB triggering two lambda functions
		4.1 Lambda stores new account data on another DyanmoDB tables for audit
		4.2 Lambda pushs the account request to the SQS queue
	5. Lambda, triggered by the schedule of AWS EventBridge, pull a message from SQS and does a request to AWS Account Factory
	6 AWS Account Factory creates of account using Control Tower and after triggers customization scripts

	

AFT Account customization procedure
 1. AWS service Catalog launches the CodePipeline of customization 
 2. CodePipeline launch first step function, which is cloning git Global and Account customization repositories
 3. The second step function is runniong the global cutomization terraform and custom scripts
 4 The second step function is running the account customization Terraform and custom script.
 
 
 Prerequisits : For the AFT installation you need to have IAM user or role with AdministratorAccess permisions, IAM role is the preferred and secured way recommended by AWS, but alternatively can use the IAM user.
 1. Deployed AWS Control Tower
 2. Install Terraform
 3. Provisioned the AFT management account(recommended on new OU)
 4 Pre-defined user with "Administrator" rights on "controller" account (For the AFT installation you need to have IAM user or role with AdministratorAccess permisions, IAM role is the preferred and secured way recommended by AWS, but alternatively can use the IAM user.)
 5 Version control system(GIT0



















		
		
		
		
		
		
		
