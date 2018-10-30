# git-playground

Repo for playing with `git`, `tags`, `workflows`, etc.

On this repo `git-flow` (`git-flow-avh`, https://github.com/petervanderdoes/gitflow-avh) is used.


## How to use

### Initializing a repo

```
git flow init 
```
This will create default branches.

### Branches

**Main branches:**
 - `master` - The stable, deployable branch, *"where the source code of HEAD always reflects a production-ready state"*
 - `develop` - Branches off `master`. *"[T]he [...] branch where the source code of HEAD always reflects a state with the latest delivered development changes for the next release. Some would call this the “integration branch”. This is where any automatic nightly builds are built from."*

**Supporting branches:**
 - `release/*` - Branches off `develop`. Must merge back into `develop` **and** `master`. *"[S]upport[s] preparation of a new production release [and] allow[s] for minor bug fixes and preparing meta-data for a release (version number, build dates, etc.)"*
 - `feature/*` - Usually branches off `develop` (or other `feature/*`) and merges back into it. *"Feature branches (or sometimes called topic branches) are used to develop new features for the upcoming or a distant future release. When starting development of a feature, the target release in which this feature will be incorporated may well be unknown at that point. The essence of a feature branch is that it exists as long as the feature is in development, but will eventually be merged back into develop (to definitely add the new feature to the upcoming release) or discarded (in case of a disappointing experiment). Feature branches typically exist in developer repos only, not in origin."*
 - `hotfix/*` - Branches off `master`. Must merge back into `develop` **and** `master`. *"Hotfix branches are very much like release branches in that they are also meant to prepare for a new production release, albeit unplanned. They arise from the necessity to act immediately upon an undesired state of a live production version."*
 
### Start a new normal feature

```
git flow feature start $feature
# add sources
git flow feature publish $feature
# add sources
git flow feature finish $feature
```

### Start working on a supernext release

```
git flow feature start $supernext
git flow feature publish $supernext


```

