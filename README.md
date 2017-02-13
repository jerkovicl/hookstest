## Testing Git Hooks

## Create symlink to folder .git/hooks
`pushd "%~dp0.git\"`  
`mklink /J /D hooks "E:\hype-kit\hooks"`  
`pause`

## Crete link to your custom .gitconfig
`git config --local include.path ../.gitconfig`

## Create link to your .gittemplates dir
```
//This tells git to copy everything in ~/.git-templates to your per-project .git/ directory when you run git init
git config --global init.templatedir '~/.git-templates'
```
```
//Create a directory to hold the global hooks and write your hooks in ~/.git-templates/hooks.
md .git-templates\hooks
```
```
//Re-initialize git in each existing repo you'd like to use this in
git init
```

## Set hooks dir for all repos (Git v2.9+)
```
//lets you centrally manage hooks for all of your local repositories.
git config −−global core.hooksPath /etc/git/hooks
```