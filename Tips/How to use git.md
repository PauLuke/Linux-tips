Clone a repository to your machine:
```
git clone https://github.com/USERNAME/REPOSITORY.git
```

Obs.: if you are trying to clone a private repository or push a repository to github you will need authentication. When asked for your password, use your token instead.

After you edit or add new files/directories you should *add* all changes:
```
git add .
```
This command updates the index using the current content found in the working tree, to prepare the content staged for the next commit.

*Commit* your modifications:
```
git commit -m "DESCRIPTIVE MESSAGE"
```

Push your changes to the GitHub repository:
```
git push origin main
```
