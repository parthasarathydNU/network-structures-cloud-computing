
In google, we have to enable APIs before we get to use it, check if you can enable it programatically

List the APIS enabled in the readme file

### do not hard code values in the tf files

**Create a vars file** where we store values for the dev and prod environment and when we run the tf apply / tf plan , we can provide this file as the var file. 

## Run tf validate against every pull request

## start looking into systemd to looka t how you can use it to run your application on the server
## Creating a subnet

Keep IpV6 disabled

Keep Subnet creation mode to custom.

Region names are different format than aws

Ip Stack type set it to IPv4 signle stack

Design the CIDR range 

Create firewall ourselves - do not accept default

Routing globally / regional - keep it regional


### Breakdown

1. Fix mistwkes in assignment 
2. 2 fix pipeline and run in remote - if possible connect vscode to remote and work
3. create github repo and set up branch protection rules
4. enablw google cloud apis
5. google cloud platform networking set up
6. connect  terraform to project and run steps
7. integration tests for end points
8. separate github runner workflow for integration tests