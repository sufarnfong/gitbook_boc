# How to use locally.

## Serve Docs Locally

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
git clone https://github.com/Bank-of-Chain-DeFi/gitbook_boc.git
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