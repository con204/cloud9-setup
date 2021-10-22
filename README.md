# Setting up Lab Environment

* Once you have logged into the AWS Management Console from your EventEngine team landing page, you will already have an
  EKS cluster and Cloud9 environment. A few additional steps are required to configure Cloud9 and install the tools as
  follows:

* Navigate to Cloud9 in the AWS Management console and launch the EKS IDE. It may take a few minutes to start.

* Select the gear icon in the upper right (or else select the "9" icon>Preferences in the upper left)
* Scroll down to "AWS Settings" in the "Preferences" tab.
  1. Under "Credentials", disable "AWS managed temporary credentials".
  2. Close the "Preferences" tab.
  3. Close the "AWS Cloud9 Welcome" and "AWS Toolkit" tabs.
* Open a new terminal tab by clicking the green "+" sign and selecting "New Terminal".
  1. Copy and run this command:
  ```bash
  aws s3 cp s3://ee-assets-prod-us-east-1/modules/bd7b369f613f452dacbcea2a5d058d5b/v5/eksinit.sh . && chmod +x eksinit.sh && ./eksinit.sh ; source ~/.bash_profile
  ```

  2. You can test access to your cluster by running the following command. The output will be a list of worker nodes.
  ```bash
   kubectl get nodes
  ```
* Note: Wait until your EKS cluster and nodegroup deployments have completed or else some of the script commands will 
  fail. If that happens, wait until deployment completes and simply re-run the script.

#### Once done, head to the [Con 204 Workshop](https://con204.github.io/advanced/350_opentelemetry)
