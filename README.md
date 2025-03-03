# Nushell
The name is explicit enough, don't you think?

## Resources
- https://www.youtube.com/watch?v=uJsZATwQ3R8

---

## Intro

Like any performant modern terminal application, Nushell is written in Rust.  
Nushell actually comes with its own language (Nu) and a philosophy behind it.  

Rather than thinking of files and data as raw streams of text, Nu looks at each input as something with **structure**.  
For example, when you list the contents of a directory, what you get is a table of rows where each row represents an item in that directory.  

Nu loves pipes and queries, and comes with a set of operators that are straightforward and easy to use.  
There's already a long list of available plugins and scripts for this new shell.

## Installation

- To install it on Windows, open a command prompt or PowerShell and run `winget install nushell`
- After installation, you can launch Nushell by typing `nu` in your command prompt or PowerShell

To set Nushell as your default shell in Windows Terminal:
- Open Windows Terminal
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
- for searching the command history, press `Ctrl + R`
- 

---

## Configuration

