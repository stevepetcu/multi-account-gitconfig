# multi-account-gitconfig
Global git configuration with support for multiple accounts (e.g., work and personal).

## Why use this repo?
These files are useful for automatically switching your global gitconfig (user email, name etc.) when you are using the same machine in multiple contexts.
For example, working on personal projects, work projects etc.

## How to use this repo?
> Note: this has only been tested on macOS.
1. Clone the repo.
2. Copy all the files to your user directory (`~` or `/Users/<your-user-name>`).
3. Edit the `.gitconfig-personal` and `.gitconfig-work` files to replace your own email/user name details.
4. Edit the `.gitconfig` file. Replace `<personal-projects/subpath>` and `<work-projects/subpath>` with the parent folder or subpath to your personal and work projects.

A finished `.gitconfig` file might look like this:

```bash
[includeIf "gitdir:**/Projects/personal-projects/**"]
  path = ~/.gitconfig-personal
[includeIf "gitdir:**/Projects/work-projects/**"]
  path = ~/.gitconfig-work
```

You can also add more entries here and more `.gitconfig-<whacky-stuff>` files. As many as you'd like.
