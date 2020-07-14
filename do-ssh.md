### ssh commands

**ssh creation**
1. ssh key should be in /home/.ssh folder 
2. to generate ssh key- 
> ssh-keygen
- the command will ask you the name of the file, you can enter it. Let say, you named it "secure-shell" . and follow the next instructions.
3. It will create two files in the same folder one is public key file .pub and the other one is a private file. In our case, it will create "secure-shell.pub" and "secure-shell"
4. It needs your attention, 
> secure-shell - never share this with anybody
> secure-shell.pub -to be share with a remote server that you want to excess
5. When you have multiple private keys then you have to add a specific key to your main identity.
> eval $(ssh-agent)
> ssh-add ~/.ssh/secure-shell

*difference ssh-add /.ssh/secure-shell V/S  ssh -i /.ssh/secure-shell ?* 

*add will set the identity of your system for a pointed key for every commit or secure shell access from now, whether -i will set temp identity pass key in case you have different keys added to the different remote workspaces.*

**GitHub access**

1. write following command to view the ssh-key (we will use secure-shell i.e. our key name). Please access the directory where your ssh key present.
> cat  .ssh/secure-shell.pub
2. The above command lists a key, copy it!!
3. Goto git account, setting > SSH and GPG keys > New ssh key and paste here 
4. that it 

**Remote access**

1. On your local machine 
> cat  .ssh/secure-shell.pub
2. The above command lists a key, copy it!!
3. go to the remote machine and write following command 
> sudo vi .ssh/authorized_key 
4. Press i button to write 
5. paste your key here and press ESC button 
6. Write - :wq

**NOTE** - *how to know which ssh is added*
>ssh-add -l