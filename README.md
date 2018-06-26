# Configure Git PHPStorm on Windows

In this article, I will guide you to configure Git PHPStorm on Windows to clone, pull, push,… with remote repository (Github, Gitlab, Bitbucket,…) 

## Install Git to work with PHPStorm

First, we make Git work with PHPStorm on your computer.
 - Download Git for Windows and install
 - Make sure correct Path to Git executable
 - File -> Settings… -> Version Control -> Git
 - Browse Path to Git executable to Git Bash - git.exe (default, PHPStorm automatic detect)
 - You can click Test button if you like :D
 
 Now, you can add, commit,… on your local. To clone, pull, push,… with remote repository, you need SSH key to authorization for Git. 
 
## Generate SSH key
 
If you has SSH key, you can skip this step. 
You can generate SSH key on Windows use PuTTYgen of Putty or follow with steps:

- Open Gist Bash
- Type ``` ssh-keygen -t rsa ``` then enter (you can set passphrase if you need)

```
$ ssh-keygen -t rsa

Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/Zet/.ssh/id_rsa):

Enter passphrase (empty for no passphrase):

Enter same passphrase again:

Your identification has been saved in /c/Users/Zet/.ssh/id_rsa.
Your public key has been saved in /c/Users/Zet/.ssh/id_rsa.pub.
The key fingerprint is:
6d:88:c1:fe:e3:70:b8:35:34:2d:56:bc:da:99:80:2c Zet@WIN-BH43BN72IRN
The key's randomart image is:
+--[ RSA 2048]----+
|                 |
|     .   .       |
|      o   o      |
|     o + = .     |
|    E = S =      |
|     . = B o     |
|      o B +      |
|       * o       |
|      . .        |
+-----------------+
```
- Go to ``` C:Usersyour_username.ssh ``` folder, you can see 2 files: ``` id_rsa & id_rsa.pub ``` . ``` id_rsa.pub ``` is public key, you can copy this content to repository remote. ``` id_rsa ``` is private key you need to authorization with server.

## Make Git PHPStorm work with remote repository

- Open ``` id_rsa.pub ``` & copy content to your repository remote (Gitlab, Bitbucket, Github, etc.)
- PHPStorm will Integration with Git, you can work with remote repository. Make sure, the keys are stored in files with correct names: ``` id_rsa: private key ``` , ``` id_rsa.pub: public key ```. 

### If you has SSH key, you can copy key to ``` C:Usersyour_username.ssh ``` folder & rename it to id_rsa.

## Note: Config file

PhpStorm supports a standard method of using multiple ssh keys, by means of creating .ssh/config file. So if you use multiple keys you can pair it up with C:UsersuserName.sshconfig to specify which key you want to use for which server 
Content ``` config ``` file:

```
Host git
    User=git
    Port=9522
    Hostname=git.example.com
    IdentityFile=C:/Users/userName/.ssh/your_key
```
You can use Port or not 
So, you can make PHPStorm & Git work with remote repository. If you enjoyed this article, please subscriber of my blog. Thank for reading


Ref links (c):
 http://vanlt.blogspot.com/2015/05/configure-git-phpstorm-on-windows.html
 https://gitlab.com/help/ssh/README#generating-a-new-ssh-key-pair


