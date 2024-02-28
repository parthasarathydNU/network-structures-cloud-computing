### Github setup - pretty interesting
Apply for a team plan
Create an organization
we have an upstream repo - which is the one that will be graded (the main branch), 
but we will have a fork on which we work locally

We will merge changes to the assignment branch on the upstream (org) repo only through a pull 
request ( pull requests can be from multiple feature branches )

delete a branch after merging to main in the fork

which branch should we commit to in the upstream branch

keep merging strategy as rebase and merge, we want to keep history linear

once the changes are merger, we first pull changes from upstream main ( the branch where the PR was merged to)
Then we push the changes to the fork's main branch. 

Feature branch -> pull request to man of upstream -> pull changes from upstream main to local main -> push changes to fork main -> create feature branch and repeat


Upstream                 Fork
main      feature       main      feature


NEVER EVER COMMIT TO YOUR MAIN BRANCH - the only thing you push to your main branch is what is in the upstream branch

### Set up github actions

.yml files not .yaml 

Create workflows for different branches

write a simple github action that on pull request to main runs one job
1. checkout the repository
2. Set up runtime, mention node version
3. run steps to build code 


### Protecting the main branch on your org repo
enable run workflows for fork in settings 
require pull requests before meeting 
require status checks to pass before merging
require branches yo be set up before merging 
require linear history to disable merge commits
do not allow bypassing settings 

but no need to do this on the fork main branch

All commits to org repo comes through a PR
use base 64 for basic auth

‘username:pass’ convert this to base64 this is the pass

password should not be stored in the database 
use Bcrypt password hashing schema with salt
