# Nushell

## Resources
- https://www.youtube.com/watch?v=uJsZATwQ3R8

---

# Intro

Like any performant modern terminal application, Nushell is written in **Rust**.  
Nushell actually comes with its own language (**Nu**) and a philosophy behind it.  

Rather than thinking of files and data as raw streams of text, Nu looks at each input as something with **structure**.  
For example, when you list the contents of a directory, what you get is a table of rows where each row represents an item in that directory.  

Nu loves **pipes** and **queries**, and comes with a set of **operators** that are straightforward and easy to use.  
There's already a long list of plugins and scripts available for this new shell.

# Installation

## On Ubuntu

We will add the official Nushell repository for Debian-based systems.  

First, add the GPG key from the repo to your local /etc/apt directory:  
`curl -fsSL https://apt.fury.io/nushell/gpg.key | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/fury-nushell.gpg`  

Then, add the repo itself:  
`echo "deb https://apt.fury.io/nushell/ /" | sudo tee /etc/apt/sources.list.d/fury.list`  

Update package lists and install Nushell:  
`sudo apt update`  
`sudo apt install nushell`  

To make Nushell your default shell:  
- get the path to the `nu` binary via `which nu`
  - this should output `/usr/bin/nu`
  - adapt the next commands if the path differs
- By default, Nushell is not listed as a valid shell in /etc/shells. To add it: `echo "/usr/bin/nu" | sudo tee -a /etc/shells`
- Use the chsh command to change your default shell: `chsh -s /usr/bin/nu`
- To confirm that Nushell is now your default shell, log out and log back in

## On Windows

- To install it on Windows, open a command prompt or PowerShell and run `winget install nushell`
- After installation, you can launch Nushell by typing `nu` in your command prompt or PowerShell

To set Nushell as your default shell in Windows Terminal:
- Press Ctrl + , to open the Settings.
- Go to "Add a new profile" and select "New empty profile".
- Fill in the following details:
  - Name: Nushell (or any name you prefer)
  - Command line: Enter the path to the Nushell executable. To get it, run `get-command nu`
  - Go to the "Startup" option in the Settings menu.
  - Select Nushell as the "Default profile".
  - Click "Save" to apply the changes

---

# Example commands

- `ls | sort-by modified` lists the contents of the current folder sorted by date of modification
- variant: `ls | sort-by modified --reverse`
- to get processes using above 5% of our CPU resources: `ps | where cpu > 5`
- for searching the command history, press `Ctrl + R`, and then start typing to filter the results
- to find a specific file in the current folder: `ls | where name == "docker.gpg"`
- to save the ouput of a command into a file: `<command> | save <fileName>`
- to display the contents of a file to the console: `open <fileName>`

---

## Configuration

... TO DO ...

---

# Auto-completion with Carapace

URL = https://carapace.sh/  

Carapace is a multi-shell completion library and binary.  
**Fun fact**: "Carapace" is french for "shell".  

Carapace was made to support **Cobra CLIs**, and populate their modules and options for every existing shell.  
Some of the most popular CLI applications built using Cobra include:
- Kubernetes (kubectl)
- AWS
- GitHub CLI (gh)
- Docker
- CoreOS
- Delve
- Dropbox
- Git LFS

## Install Carapace on Ubuntu

Add the Fury.io repository to your system:  
`echo "deb [trusted=yes] https://apt.fury.io/rsteube/ /" | sudo tee /etc/apt/sources.list.d/fury.list`  

Update the package list:  `sudo apt-get update`  

Install Carapace: `sudo apt-get install carapace-bin`
