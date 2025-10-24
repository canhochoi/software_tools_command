For uploading to git, if I already have ssh keys generated, do the followings: 

```bash
git remote set-url origin git@github.com:repo_address_on_git
```
where repo_address_on_git can be `canhochoi/regression.git`

Then, test the connection:
```bash
ssh -T git@github.com
```

Then, push:
```bash
git branch -M main
git push -u origin main
```
