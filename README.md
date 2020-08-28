# NIPTool

NIPTool is a visualisation tool for NIPT data...

## Installation


```bash
git clone https://github.com/Clinical-Genomics/NIPTool.git
cd NIPTool
pip install -r requirements.txt -e .
```

## Release model
NIPTool development is organised on a flexible Git "Release Flow" branching system. This more or less means that we make releases in release branches which corresponds to stable versions of Vogue.

### Steps to make a new release:

1) Create a release branch from master named `version_X.X.X` 
2) Update change log with the new version.
3) Update NIPTool/__init__.py with the new version.
4) Make a PR to master, 
	- Name PR `release version X.X.X`
	- Justify if its a patch/minor/major version bump
	- Paste the latest changelog to the text body
	- get it approved and merge to master. **Dont delete the release branch!**
5) Make a [new release](https://github.com/Clinical-Genomics/NIPTool/releases/new).
	- Name tag version as `vX.X.X`
	- Set target to the release branch
	- Make descriptive title
	- Paste latest changelog to the text body
	- Release!

### Deploying to production

Use `update-nipt-prod.sh` script to update production both on Hasta and clinical-db. **Please follow the development guide and `servers` repo when doing so. It is also important to keep those involved informed.**

## Back End
The NIPT database is a Mongo database consisting of following collections:

- **batch** - holds batch level information.
- **sample** - holds sample level information.
- **user** - holds user names, emails and roles.


## CLI
The CLI has two base commands - load and run. The load command is for loading batch and sample data into the nipt database, and the run command is for running the web application.

### Load 
```
Usage: nipt -c <config.yaml> load batch  [OPTIONS] ...
```

  
### Run
```
Usage: nipt run [OPTIONS] ...

```
