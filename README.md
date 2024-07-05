This is my Home Assistant configuration-as-code repo. The idea is to manage as much of my Home Assistant configuration as possible through this repo.

# Setup

## Bootstrapping an existing installation

For an existing installation, we have existing configuration to merge with the repo:

#. Install the SSH Addon if you haven't already.
#. Login to the instance using the SSH addon (Web UI is fine).
#. All existing configuration will be located under the `config/` subdirectory. `cd` to that directory.
#. Initialize this directory as a git repository and setup initial `.gitignore`:

```bash
git init .
# Set main branch as default (optional)
git branch -m main
# Configure git with your committer name and email
git config --global --edit
# Create initial empty commit
git commit --allow-empty -m "Initial commit"
# Download .gitignore from this repo
curl --fail --silent --show-error --location --remote-name https://github.com/teekennedy/hass-config/raw/main/.gitignore
git add .gitignore
```

#. With `.gitignore` in place, run a `git status` and make sure that all files meant for temporary storage / caching and especially ones that contain sensitive info are being ignored. Go through each file individually before adding to the commit. Do not skip this step!
#. With each file / directory in the repo successfully added to the commit or added to .gitignore, commit the changes:
`git commit -m "Initial import of existing config"`
