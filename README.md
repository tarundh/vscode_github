Step 1: Get SSH Access
Connect to your server via SSH. (To do this please, follow this guide.)

Step 2: Generate SSH Key (Master Credentials Only)
Once the SSH connection has been established, you need to generate SSH keys for directly connecting your GitHub or Bitbucket repositories without providing a username or password every time.

Navigate to your desired web application’s webroot (public_html) and then type the following command to generate public and private RSA key pair.

ssh-keygen -t rsa -C your_email@example.com
#replace your_email@example.com with your email address.
Hit Enter to save the key in the default location (/home/master/.ssh/id_rsa). Hit Enter twice for no/empty passphrase.

Your SSH keys will be saved at the default location. Run the following command to view the generated public SSH key.

cat /home/master/.ssh/id_rsa.pub
Copy the public key text carefully starting from ssh-rsa and ending in your email address. This text will be used in the next step.


Step 3: Upload the SSH Public Key to Your Git Repository
We are using a Github account for this demonstration. If you prefer another Git service, you will have to find the equivalent way of completing this step.

Log into your GitHub account and choose your desired repository (which you want to connect to your web application).  Then, navigate to Settings and click on Deploy Keys.

Click on Add Deploy Key button to add the SSH key we copied in step 3. Paste the content into the Key field on Github. You can give a name to this key in the title field (e.g. Demo).

Check Allow write access option to give write access (push) to your repository

Click on Add Key button to save the SSH key.

