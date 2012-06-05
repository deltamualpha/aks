## aks - AWS Key Switcher

* Do you have too many IAM accounts?
* Are you bouncing between several AWS accounts, multiple times everyday?
* Searching for a way to manage all your access and secret keys?
* Is it a pain to generate signing certificates for all your IAM accounts?

aks is here to help.

### How aks works

aks modifies the running bash environment variables that are needed by the
AWS CLI tools. It does this by creating a subdirectory in $HOME/aws/auth
for each IAM account - using a name you specify. When creating a new account,
aks will auto generate a signing ceritificate for it. aks also has the option to
import the environment for locating the AWS CLI tools (e.g. EC2_HOME,
EC2_AMITOOL_HOME, AWS_IAM_HOME, etc. etc.)

### How to install

	git clone git://github.com/dialt0ne/aks.git
	cd aks
	mkdir $HOME/aws
	cp aks.sh global.sh $HOME/aws

### Configuration

	cd $HOME/aws
	vi aks.sh global.sh
	# customize variables as needed

### Usage

	source $HOME/aws/aks.sh
	
	usage:
	   aks create [newaccountname]
	   aks id
	   aks list
	   aks use [accountname]

