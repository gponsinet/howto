# How to Git

## Setup

### Config

Add this to .gitconfig in your $HOME directory
```
[user]
	name = YOUR_USERNAME
	email = YOUR_EMAIL
	# signingkey = YOUR_GPG_SIGNINGKEY
[core]
	editor = YOUR_EDITOR
[pull]
	rebase = true
[commit]
	# gpgsign = true
[diff]
	tool = vimdiff
[difftool]
	prompt = false
[alias]
	d = difftool
[gc]
	auto = 0
[gpg]
	program = gpg
[url "git@github.com:"]
	insteadOf = http://github.com/
[url "git@github.com:"]
	insteadOf = https://github.com/
[http]
	cookiefile = .gitcookies
```

### SSH

Create your keypairs with ssh-keygen
```bash
ssh-keygen -t ed25519 # ed25519 is cool
```

### Github

Copy the content of your public key in `~/.ssh/id_ed25519.pub`.
Go to https://github.com/settings/ssh/new.
Paste the public key content in the form.
Go to https://github.com/YOUR_USERNAME.keys to see your keys.
