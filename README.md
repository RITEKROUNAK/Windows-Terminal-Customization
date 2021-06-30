# Windows-Terminal-Customization

Most of us (developers) love using terminal and I personally prefer Terminal over GUI especially when it comes to Git BUT if you're a Windows user, the command prompt is so boring.

Have you ever seen Mac OS terminals? Aren't they cool? Let's try to change our windows boring command prompt to something like this:

There are several steps to follow.

- Downloading Windows Terminal
- Installing Modules
- Changing Fonts
- Changing Theme

# Downloading Windows Terminal
By default, Windows provides <strong>Command prompt</strong> and <strong>PowerShell</strong>. We will not modify any of these but rather download <a href="https://github.com/microsoft/terminal">Windows Terminal</a>.
It is recommended to download it from <a href="https://www.microsoft.com/en-in/p/windows-terminal/9n0dx20hk701?rtc=1&activetab=pivot:overviewtab">Microsoft Store </a>. Make sure your Windows version is the latest.

Once it's downloaded and installed, open it from Windows Start by simply typing Windows Terminal

By default, it looks something like this

# Installing Modules
There are two modules that we need to make our terminal looks awesome.

<a href="https://github.com/JanDeDobbeleer/oh-my-posh">oh-my-posh</a>
<a href="https://github.com/dahlbyk/posh-git">posh-git</a>
Oh My Posh is a module that helps you to decorate your Powershell and make it look more colorful.
Posh git is a module that helps you to provide autocomplete for git commands, paths, and branches.

To install these two modules, run Windows Terminal as Administrator.

Execute
```
Install-Module oh-my-posh

```
Next is to install posh-git
```
Install-Module posh-git

```

Now that we have both modules installed, it's time to import them.
To do that, execute the following commands
```
Set-ExecutionPolicy Unrestricted

```

Now Execute
```
Import-Module oh-my-posh
Import-Module posh-git
Set-PoshPrompt Paradox
```

The change looks a bit odd, there is a small blue triangle after ~ (Tilda). Let's fix that later.
There is one other problem that every time you start Windows Terminal, you'll need to import the modules again.

To fix this issue, we need to create a file in the Windows Terminal folder and paste all these commands there.

If you do
```
echo $profile
```

You'll get a file path in return, that's the file, which is executed every time we start Windows Terminal
We just need to simply add those import commands to this file.
To do that,
```
notepad $profile
```

This will ask you to create this file if it doesn't exist.

Paste the following commands and save the file.
```
Import-Module oh-my-posh
Import-Module posh-git
Set-PoshPrompt Paradox
```

Now try restarting your Terminal and it will still have the change.
