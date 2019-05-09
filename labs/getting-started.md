# Getting Started


[Apache OpenWhisk](http://openwhisk.incubator.apache.org/) is a freely available open-source Serverless (FaaS) platform. The cool thing about this is that we can run it on any cloud or on prem. As developers we don't want to manage all the servers though (hence serverless, duh!) so it's easiest to use a managed OpenWhisk provider.

[IBM Cloud Functions](https://console.bluemix.net/openwhisk/) is a an OpenWhisk provider and has a free account you can sign up for and use for these workshops.

### Registering for a free IBM Cloud Account

1. If you don't have one already, sign up for a free IBM Cloud Account [here](https://ibm.biz/Bd2w6g).

2. Verify your account via the email the platform sends you.

3. Log in to your IBM Cloud Account.

### Install the IBM Cloud CLI

Apache OpenWhisk has it's own [CLI](https://github.com/apache/incubator-openwhisk-cli) (command line interface) `wsk`. To make authenticating with the IBM platform easier we are going to use the IBM Cloud CLI `ibmcloud` for these workshops. This CLI provides a wrapper for the `wsk` CLI.

1. Go to [this docs link](https://cloud.ibm.com/docs/cli?topic=cloud-cli-install-ibmcloud-cli) and follow the short instructions to download and install the CLI.

### Log in to the IBM Cloud CLI

1. Log in to the IBM Cloud CLI using the following command from a terminal:

   ```
   $ ibmcloud login
   ```

2. Choose an API endpoint from the list.
   ***IBM Cloud Functions is available in the following regions: `eu-de`, `eu-gb`, `jp-tok`, `us-east` and `us-south`. Lite account users must choose their default account region.***
   If you don't know what your default region is try `eu-gb` first.

   ```
   Select an API endpoint:
   1. eu-de - https://api.eu-de.bluemix.net
   2. au-syd - https://api.au-syd.bluemix.net
   3. us-east - https://api.us-east.bluemix.net
   4. us-south - https://api.ng.bluemix.net
   5. eu-gb - https://api.eu-gb.bluemix.net
   6. Enter a different API endpoint
   Enter a number>
   ```

3. Enter account credentials for your IBM Cloud account.

  ```
  Email> user@email.com

  Password>
  Authenticating...
  OK

  Select an account (or press enter to skip):
  1. John Smith's Account (xxx)
  Enter a number>

  API endpoint:     https://api.eu-gb.bluemix.net (API version: 2.92.0)
  Region:           eu-gb
  User:             user@email.com
  Account:          No account targeted, use 'bx target -c ACCOUNT_ID'
  Resource group:   No resource group targeted, use 'bx target -g RESOURCE_GROUP'
  Org:
  Space:

  ```

4. Run the following command to configure the organisation and space the CLI is targeting.

  ```
  $ ibmcloud target --cf
  Targeted org user@email.com
  Targeted space dev

  API endpoint:     https://api.eu-gb.bluemix.net (API version: 2.92.0)
  Region:           eu-gb
  User:             user@email.com
  Account:          No account targeted, use 'bx target -c ACCOUNT_ID'
  Resource group:   No resource group targeted, use 'bx target -g RESOURCE_GROUP'
  Org:              user@email.com
  Space:            dev
  ```

### Install IBM Cloud Functions CLI plugin

1. Use this command to install the Cloud Functions plugin for the IBM Cloud CLI.

 ```
 $ ibmcloud plugin install cloud-functions
 Looking up 'cloud-functions' from repository 'Bluemix'...
 Plug-in 'cloud-functions 1.0.7' found in repository 'Bluemix'
 Attempting to download the binary file...
  11.13 MiB / 11.13 MiB [=================================================================================] 100.00% 9s
 11665633 bytes downloaded
 Installing binary...
 OK
 Plug-in 'cloud-functions 1.0.7' was successfully installed into /home/user/.bluemix/plugins/cloud-functions.
 ```


### Test IBM Cloud Functions From The CLI

1. Run the following command to invoke a test function from the command-line.

 ```
 $ ibmcloud wsk action invoke whisk.system/utils/echo -p message hello --result
 {
     "message": "hello"
 }
 ```

*If this command executes successfully, you have verified that the IBM Cloud CLI and Cloud Functions plugin have been installed and configured correctly. If this does not work, please contact the workshop organiser to provide assistance!*

🎉🎉🎉 **Congratulations, you've successfully registered an IBM Cloud account, configured the IBM Cloud CLI for Cloud Functions development and executed your first serverless function! Let's start using the platform to create our own serverless applications…** 🎉🎉🎉

### Next Lab
[Creating and Managing Actions](/labs/creating-and-invoking-actions.md)