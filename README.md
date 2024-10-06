# git-filter-repo-howto
HowTo for git-filter-repo

## Change Commiter name and email
use with caution! 
(see DISCUSSION from git-filter-repo Manual Page) 

```bash
# 1. Download [git-filter-repo](https://github.com/newren/git-filter-repo)
curl https://raw.githubusercontent.com/newren/git-filter-repo/refs/heads/main/git-filter-repo > git-filter-repo

# 2. clone repository
# replaye with actual SSH url
git clone git@github.com:<repo>.git
# optionally `git log` to show commits with author info

# 3. create mailmap
# replace with actual info for author and email
echo "NewAuthor <new@mail> <old@mail>" > mailmap

# 4. run git-filter-repo
# replace with actual repo
cd repo
python3 ../git-filter-repo --mailmap ../mailmap --partial

# 5. push back
git push --force
