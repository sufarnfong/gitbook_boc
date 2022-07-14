# Bank of Chain Documentation

## Introduction

Official documentation for BOC. This repo is used to sync changes from Markdown files (.md) with the DOC's website. The different repository branches are tracked by GitBook to feed each language variant on the documentation.

## Updating versions

Use the following steps to update a specific version. For example, to update the Chinese docs:

- Clone the repo and change to the branch you want to work on.
```
git clone https://github.com/Bank-of-Chain-DAO/gitbook_boc.git
git checkout zh
```
- You will update, ```add``` and ```commit``` everything and push the zh branch to Github
```
git add .
git commit -m "new commit"
git push
```
- Go to documentation website and confirm everything updated as expected. It may take a minute or two for the changes to sync.

## Volunteering

Volunteers who wish to help improve our translations can volunteer using this [form](https://docs.google.com/forms/d/e/1FAIpQLScj-J4PhhZCeoRy5MvwlXj1EqipYp6wZWhx5QwIvasuFllnTg/viewform).

## How to test locally.

Is highly recommended to test locally the plotting of the changes done, especially on the first interactions with GitBook and Markdown 

### Install npm
```
apt-get install npm
```
### Install gitbook
```
npm install gitbook-cli -g
```

### Clone Repository
```
git clone https://github.com/Bank-of-Chain-DAO/gitbook_boc.git
```
### Install Plugins
```
gitbook install
```
In case this step failure we recommend this solution: [LINK](https://flaviocopes.com/cb-apply-not-a-function/)

### Cd to you repo location
```
cd path/to/repo
```
### Build
```
gitbook build
```
### Run Serve
```
gitbook serve
```
### Browse
The documentation is served at localhost:4000 by default.
