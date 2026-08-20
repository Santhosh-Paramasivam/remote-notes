---
id: powershell-basics.md
aliases: []
tags:
  - #powershell
  - #windows
  - #shell
  - #cli
---

# PowerShell Basics

- There are automatic local variables in PowerShell that contain valuable info, such as `$PSVersionTable`

- Cmdlets -> a compiled cli program

- PowerShell commands have a 'Verb-Noun' syntax that makes them easily discoverable

## Getting help 

- [getting-help](https://learn.microsoft.com/en-us/powershell/scripting/learn/ps101/02-help-system?view=powershell-7.6)

- `Get-Command` -> To look up a command and whether it exists. Regex can be used when looking up commands

- `Get-Help` -> Gets the manpage-like help output for a command

- `Get-Member` -> not yet studied

- When using get-help, there are multiple parameter sets that appear in SYNTAX section. Choosing certain parameters locks you into a particular parameter set. The parameter sets are mutually exclusive.

- `Get-Help -Name Get-Help -Full` -> Shows syntax in a human readable format

- `Get-Help -Name Get-Help -Online` -> Shows syntax in a human readable format