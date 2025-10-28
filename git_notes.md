For uploading to git, enter the folder you want to upload. 

1. Check the git status with `git status`, if not a git repository, do `git init`
2. Do `vi .gitigore` and add any files you don't want to upload
3. Add files to be uploaded (e.g., `git add abc.py def.R` or upload all files with `git add .`)
4. Verify staged files with `git status`
5. Write commit message with `git commit -m "Add files ..."`
6. Set up git repo on github website, copy http URL (e.g., `https://github.com/canhochoi/Epimutation_CpG.git`) or SSH URL (e.g., `git@github.com:canhochoi/Epimutation_CpG.git`)  
7. Link the repo with `git remote add origin http URL/SSH URL in step 6`
If you already have ssh keys generated, do the followings: 

```bash
git remote set-url origin git@github.com:repo_address_on_git
```
where repo_address_on_git can be `canhochoi/regression.git`

8. Test the connection:
```bash
ssh -T git@github.com
```

9. Push:
```bash
git branch -M main
git push -u origin main
```

To create SSH keys, do the followings:


0. Generate public and private key if you don't have, for example:  

```ssh-keygen -t key_name -C "your_email@example.com" ```

  

1. Assign key to SSH Agent 

```eval "$(ssh-agent -s)" 

ssh-add ~/.ssh/id_rsa where id_rsa is private key  
```
 

Then, add to .bashrc 
```
eval "$(ssh-agent -s)" >/dev/null 

ssh-add ~/.ssh/id_rsa 2>/dev/null 
```
 
And then source the .bashrc 
 
Create a config file at .ssh/ with the following content: 

```
Host github.com 

   AddKeysToAgent yes 

   IdentityFile ~/.ssh/id_rsa 
```
 

Then make it private with ```chmod 600 ~/.ssh/config ```
