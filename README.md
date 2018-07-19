# SFDX  App

This app demonstrates a bug in Salesforce DX where field permissions are not pulled as expected for the System Administrator profile.

The bug was observed with `sfdx` 6.24.0-9405104f19

## Dev, Build and Test

To reproduce the bug, clone this repo and then perform the following steps using the `master` branch.

```sh
# Create a scratch org
sfdx force:org:create -f config/project-scratch-def.json -a bug

# Push the source to the scratch org
sfdx force:source:push -u bug

# Open the scratch org
sfdx force:org:open -u bug

# Edit the System Administrator profile and grant Edit permission
# to the Year Started field on the Account object

# Pull the source from the scratch org.
# You would expect to see a change based on the fact that you granted
# Edit permission to a field, but DX reports no changes.
sfdx force:source:pull -u bug
```


## Resources


## Description of Files and Directories


## Issues


