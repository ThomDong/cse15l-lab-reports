# How to log into a course-specific account on ieng6 and how to download Visual Studio Code on your computer.
## STEP 1: Finding your CSE 15L account and resetting the password
Find your CSE 15L account
click this [link](https://sdacs.ucsd.edu/~icc/index.php)
When you open this link you will see something like below:
![image](https://user-images.githubusercontent.com/130010181/230690405-c8a8ad41-1453-47b6-bc6a-5fa82aeb8ef4.png)
Type in your **UCSD username** for the username and **PID** for Student ID.
Then click submit.
After you click submit, you will see this as it shows below:
![image](https://user-images.githubusercontent.com/130010181/230690454-63976511-7844-423c-9542-c18d88874d5d.png)
You will see your CSE 15L account under **Addtional Accounts**. Write your CSE 15L somewhere safe because you will need this to change the CSE 15L account password.
The two letters after 23 are specific for your account.
Just above **Addtional Accounts**, click on the blue underlined **change your password**
![image](https://user-images.githubusercontent.com/130010181/230691276-bcc1b394-f19b-4370-abfe-af10c36fa408.png)
Then, you will see something like this.
Now, under **Enter your username:**, type in your CSE 15L account that you wrote somewhere. Then, click continue.
![image](https://user-images.githubusercontent.com/130010181/230691396-e23ff64c-1d29-4473-9dd3-6ca7b417bc6c.png)
You will see this. Click on **I want to reset my course-specific account password.**
![image](https://user-images.githubusercontent.com/130010181/230691470-3e699877-82a3-43d1-b1c0-b7de09d00f11.png)
You will now see this, finish your Duo Multi-Factor Authetication.
![image](https://user-images.githubusercontent.com/130010181/230691541-742e5122-8d0f-4d3a-8822-1f3b07af5a7d.png)
After the authentication, you see Confirm Your Email Address page.
Click on **Yes**.
Check your UCSD Gmail. 
![image](https://user-images.githubusercontent.com/130010181/230691611-040c3ba3-ace0-4385-b909-3fcd8b0e657b.png)
You should have received this email.
Click on **UC San Diego Password reset page**.
![image](https://user-images.githubusercontent.com/130010181/230691678-0421d7f0-ffe1-4b0f-8834-78b754dbbbf6.png)
Enter new password and confirm new password and then click **CHANGE PASSWORD**
## STEP 2: Downloading Visual Studio Code
Now you are ready to download Visual Studio code.
Click on this [link](https://code.visualstudio.com/)
![image](https://user-images.githubusercontent.com/130010181/230691873-b1333877-1613-4596-86ce-cd894db55b0a.png)
Click on **DOWNLOAD**.
![image](https://user-images.githubusercontent.com/130010181/230691901-51459cec-4a8c-47e1-9ec4-b72cb221d339.png)
Download Visual Studio Code depending on your Operating System.
Once your Visual Studio Code is finished downloading, you are ready to have some fun with it on the terminal.
## STEP 3: Remotely logging into the ieng6 server on VS Code terminal
Open **Visual Studio Code**
![image](https://user-images.githubusercontent.com/130010181/230692027-53aae710-1418-4db7-a599-c5b9bdbc3262.png)
Click on **New File**
Name it any way you please.
![image](https://user-images.githubusercontent.com/130010181/230692203-ecc2b0d5-5323-4356-9bea-7bbb9276b1ca.png)
From there click **Create File**
![image](https://user-images.githubusercontent.com/130010181/230692290-6c289b20-3deb-4821-9df0-efec6d0ba2fa.png)
You are almost there. Hang in there. Now, click on **Terminal**. It is located near the top left. Then, click on **New Terminal**.
Now, let us connect remotely on Terminal. Type in ssh your CSE 15L account plus @ieng6.ucsd.edu. So, if your CSE 15L account is cs15lsp23ab, you will have to type in **ssh cs15lsp23ab@ieng6.ucsd.edu** right after the $ on the terminal. Then, hit enter.
![image](https://user-images.githubusercontent.com/130010181/230693665-ecd181ec-6a97-4176-96ab-aa0dc5d69322.png)
Now enter your password and hit enter.
![image](https://user-images.githubusercontent.com/130010181/230693717-a6bc20c4-b185-440e-a75e-7a90c079a798.png)
Congrats!! You finally logged in remotely to the server.
## STEP 4: Trying some commands
Now, you are ready play with some commands on the terminal.
Type in something like
1. `cd`
2. `ls`
3. `pwd`
4. `mkdir`
5. `cp`
![image](https://user-images.githubusercontent.com/130010181/230694105-d34b1ec3-ad46-4e00-b825-00c9411c2ddb.png)
You will see these after you try those commands.
I will explain what each command means:
* cd means changing directory. This command lets you go into another directory. You need to type in the name of the directory after cd. If the name of directory is dir2, you need to type in cd dir2
* ls stands for list. ls lists all the files within your current directory.
* pwd stands for print working directory. pwd prints the full path of your current directory. It lists all the parent directories.
* mkdir stands for make directory. This command makes or creates a directory.
* cp stands for copy. This command lets you create a copy of the contents of the file or directory.

Thank you for reading my blog post. You did well!!



