`git clone https://github.com/hymced/test.git test-copy`

branch to test CredentialHelperSelector, which appears when pushing to GitHub since the installation of Ruby On Rails (railsinstaller-4.0.1.exe)

```bash
git checkout -b test-CredentialHelperSelector
git push --set-upstream origin test-CredentialHelperSelector:test-CredentialHelperSelector-remote
git push -u origin test-CredentialHelperSelector:test-CredentialHelperSelector-remote
```

- creates a new upstream branch on the remote repository named `test-CredentialHelperSelector-remote`
- pushes local tracking branch named `test-CredentialHelperSelector` from local repo to the origin
- creates a remote tracking branch on local repo named `origin/test-CredentialHelperSelector-remote`

https://stackoverflow.com/questions/33503080/learning-git-tracking-vs-setting-upstream-u-for-remotes/33503255#33503255
> `git push origin master` explicitly says "push the local branch 'master' to the remote named 'origin'". This does not define a persistent relationship, it just executes a push this one time. Note that the remote branch is assumed to be named "master".\
> `git push -u origin master` is the same thing, except it first adds a persistent tracking relationship between your local branch "master" and the remote named "origin". As before, it is assumed the remote branch is named "master".\
> If you have done a push with `-u` already, then the relationship is already defined. In the future, you can simply say `git push` or `git pull`, and git will automatically use the defined remote tracking branch without being told explicitly.\
> You can view your tracking relationships with `git branch -vv`, which will list your local branches along with their current HEAD commit and, if one is set, the remote tracking branch.

# CredentialHelperSelector

```
Select a credential helper
<no helper>
cache--daemon
cache
store
wincred
manager-core
(checkbox) Always use this from now on
```

# Docu

https://git-scm.com/doc/credential-helpers
> ### Git credential helpers
> This page lists available credential helpers.
> ### Included in Git
> - git-credential-store: saves credentials in plaintext. https://git-scm.com/docs/git-credential-store
> - git-credential-cache: holds credentials temporarily in process memory. Not available on Windows. (Note that since credentials are lost when the cache expires or system restarts, this is inconvenient to store long-lived personal access tokens.) https://git-scm.com/docs/git-credential-cache
> ### Platform specific storage
> - git-credential-osxkeychain: stores in macOS keychain. Included in macOS Git installations.
> - git-credential-libsecret: stores in Linux secret service such as GNOME Keyring or KDE Wallet. Packaged in many Linux distributions.
> - git-credential-wincred: stores in Windows Credential Manager. Included with Git for Windows. https://support.microsoft.com/en-us/windows/accessing-credential-manager-1b5c916a-6a16-889f-8581-fc16e8165ac0
> ### OAuth
> The following cross-platform helpers support authentication using OAuth. Initial authentication opens a browser window to the host. Subsequent authentication happens in the background.
> - Git Credential Manager: included with Git for Windows. Supports multiple credential stores. https://github.com/git-ecosystem/git-credential-manager
> - git-credential-oauth: included in many Linux distributions.

https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage\
> Git has a credentials system that can help with this. Git has a few options provided in the box:
> - The default is not to cache at all. Every connection will prompt you for your username and password.
> - The “cache” mode keeps credentials in memory for a certain period of time. None of the passwords are ever stored on disk, and they are purged from the cache after 15 minutes.
> - The “store” mode saves the credentials to a plain-text file on disk, and they never expire. This means that until you change your password for the Git host, you won’t ever have to type in your credentials again. The downside of this approach is that your passwords are stored in cleartext in a plain file in your home directory.
> - If you’re using macOS, Git comes with an “osxkeychain” mode, which caches credentials in the secure keychain that’s attached to your system account. This method stores the credentials on disk, and they never expire, but they’re encrypted with the same system that stores HTTPS certificates and Safari auto-fills.
> - If you’re using Windows, you can enable the Git Credential Manager feature when installing Git for Windows or separately install the latest GCM as a standalone service. This is similar to the “osxkeychain” helper described above, but uses the Windows Credential Store to control sensitive information. It can also serve credentials to WSL1 or WSL2. See GCM Install Instructions for more information.\
> [Git for Windows](https://gitforwindows.org/)\
> [latest GCM](https://github.com/git-ecosystem/git-credential-manager/releases/latest)\
> [GCM Install Instructions](https://github.com/git-ecosystem/git-credential-manager#readme)

# Web Archive History
https://web.archive.org/web/*/https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage

### winstore
https://web.archive.org/web/20141029153945/https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage\
https://web.archive.org/web/20151019062240/https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage
> If you’re using Windows, you can install a helper called “winstore.” This is similar to the “osxkeychain” helper described above, but uses the Windows Credential Store to control sensitive information. It can be found at https://gitcredentialstore.codeplex.com.

### wincred
https://web.archive.org/web/20151119082356/https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage\
https://web.archive.org/web/20170202120018/https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage
> If you’re using Windows, you can install a helper called “wincred.” This is similar to the “osxkeychain” helper described above, but uses the Windows Credential Store to control sensitive information.

### manager / Git Credential Manager for Windows
https://web.archive.org/web/20170309220302/https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage\
https://web.archive.org/web/20220122015826/https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage
> If you’re using Windows, you can install a helper called “Git Credential Manager for Windows.” This is similar to the “osxkeychain” helper described above, but uses the Windows Credential Store to control sensitive information. It can be found at https://github.com/Microsoft/Git-Credential-Manager-for-Windows.

### manager-core / Git Credential Manager
https://web.archive.org/web/20220303175221/https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage

# StackOverflow

https://stackoverflow.com/questions/38333752/trying-to-understand-wincred-with-git-for-windows-confused
> MSDN documentation for Windows Credential Management.\
> https://msdn.microsoft.com/en-us/library/windows/desktop/aa374792(v=vs.85).aspx\
> The Git interface just uses the provided API to store your credentials securely. Functions like CredEnumerate and CredWrite get used to check the stored credentials and add or update them.

https://stackoverflow.com/questions/35942754/how-can-i-save-username-and-password-in-git/64744371#64744371
> wincred deprecated\
> https://github.com/Microsoft/Git-Credential-Manager-for-Windows#notice-this-project-is-no-longer-being-maintained-warning

https://stackoverflow.com/questions/66795897/is-control-panels-credential-manager-same-as-gits-credential-helpers-credentia/66839742#66839742
> A credential helper is an executable responsible for storing and retrieving credentials for git.\
> The windows credential manager is a place for storing credentials in Windows.\
> Both manager and manager-core credential helpers use the windows credentials manager to store credentials (they are basically the same helper, but manager uses dotnet framework and manager-core uses dotnet core).\
> https://github.com/microsoft/Git-Credential-Manager-Core\
> https://github.com/microsoft/Git-Credential-Manager-for-Windows\
> https://git-scm.com/docs/gitcredentials

https://stackoverflow.com/questions/66795897/is-control-panels-credential-manager-same-as-gits-credential-helpers-credentia/66839742#66839742
> Git credential helper is just a utility that comes with the Git standalone installation.\
> Windows Credential Manager is where your credentials (user name & passcode) for git repos (accounts) and everything else like Microsoft account and other accounts are managed and stored.

https://github.com/Microsoft/Git-Credential-Manager-for-Windows#notice-this-project-is-no-longer-being-maintained-warning
> Git Credential Manager for Windows is no longer being maintained. The cross-platform Git Credential Manager Core (GCM Core) is the official replacement.\
> https://aka.ms/gcmcore redirects to https://github.com/git-ecosystem/git-credential-manager
>
> GCM Core is included as an optional component of Git for Windows 2.28 and will be made the default credential helper as of Git for Windows 2.29. GCM Core can also be manually installed from this page.\
> https://github.com/microsoft/Git-Credential-Manager-Core/releases/latest redirects to https://github.com/git-ecosystem/git-credential-manager/releases/latest

https://github.com/git-ecosystem/git-credential-manager
> Git Credential Manager (GCM) is a secure Git credential helper built on .NET that runs on Windows, macOS, and Linux. It aims to provide a consistent and secure authentication experience, including multi-factor auth, to every major source control hosting service and platform.\
> GCM supports (in alphabetical order) Azure DevOps, Azure DevOps Server (formerly Team Foundation Server), Bitbucket, GitHub, and GitLab. Compare to Git's built-in credential helpers (Windows: wincred, macOS: osxkeychain, Linux: gnome-keyring/libsecret), which provide single-factor authentication support for username/password only.\
> GCM replaces both the .NET Framework-based Git Credential Manager for Windows and the Java-based Git Credential Manager for Mac and Linux.

https://github.com/git-ecosystem/git-credential-manager/blob/main/docs/rename.md
> Git Credential Manager Rename\
> In November 2021, "Git Credential Manager Core" was renamed to simply "Git Credential Manager", dropping the "Core" moniker.\
> At the time, the actual exectuable name was not updated and continued to be git-credential-manager-core. As of 2.0.877, the executable has been renamed to git-credential-manager, matching the new project name.

https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/install.md#git-for-windows-star
> Git for Windows ⭐\
> GCM is included with Git for Windows. During installation you will be asked to select a credential helper, with GCM listed as the default.\
> (Git Credential Manager Core)

https://cran.r-project.org/web/packages/gitcreds/vignettes/helper-survey.html
> ### `manager`
> This was Git Credential Manager for Windows, and it is the default helper on Windows for git 2.28.0. In git 2.29.0 it is not the default any more, and it is deprecated in favor of manager-core. It is still installed, though.
> ```git credential-manager```
> ### `manager-core` (on Windows, before version 2.0.246-beta)
> Not installed by default (git 2.28.0), but this is supposed to be the future canonical implementation.
> ### `manager-core` (on Windows, from 2.0.246-beta)
> This is now the version that is the default helper in git 2.29.0 and later. manager is still installed, but the default system config sets manager-core. 

```
git credential-manager --version
2.0.935+8b4735fc7b
git credential-manager-core --version
git credential-manager-core --version
warning: git-credential-manager-core was renamed to git-credential-manager
warning: see https://aka.ms/gcm/rename for more information
2.0.935+8b4735fc7b
```

https://kevinfiol.com/blog/getting-rid-of-the-credential-helper-selector-on-git-for-windows/
```
git config --system --unset credential.helper
git config credential.helper store
```

# Notes & How to solve

```
git config --list

credential.helper=helper-selector
remote.origin.url=https://github.com/hymced/test.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.main.remote=origin
branch.main.merge=refs/heads/main
branch.test-CredentialHelperSelector.remote=origin
branch.test-CredentialHelperSelector.merge=refs/heads/test-CredentialHelperSelector-remote
```

```git config --system --list```

Windows Credentials can be opened with `rundll32.exe keymgr.dll,KRShowKeyMgr`

The window appearing appearing is from this exe:
```
C:\RailsInstaller\Git\mingw64\bin\git-credential-helper-selector.exe
```

The other one that was already installed from my initial Git Bash installation:
```
C:\Program Files\Git\mingw64\bin\git-credential-helper-selector.exe
C:\Program Files\Git\mingw64\bin\git-credential-manager.exe
C:\Program Files\Git\mingw64\bin\git-credential-manager-core.exe
C:\Program Files\Git\mingw64\libexec\git-core\git-credential-wincred.exe
```
Since the installation, VS Code Terminal still defaults to bash but with `Command line: C:\RailsInstaller\Git\bin\bash.exe '--login' '-i'`

```cmd
C:\Users\Ced>echo %PATH%
C:\Python311\Scripts\;C:\Python311\;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files\nodejs\;C:\ProgramData\chocolatey\bin;C:\Program Files\dotnet\;C:\RailsInstaller\Git\bin;C:\RailsInstaller\Ruby3.1.3\bin;C:\Users\Ced\AppData\Local\Microsoft\WindowsApps;C:\Users\Ced\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\Ced\AppData\Roaming\npm;C:\Users\Ced\AppData\Local\Programs\mongosh\;C:\Program Files\MongoDB\Server\6.0\bin\
```

In the end, I just unintalled RailsInstaller (Rails development environment installer for Windows), after:
```
C:\Python311\Scripts\;C:\Python311\;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files\nodejs\;C:\ProgramData\chocolatey\bin;C:\Program Files\dotnet\;C:\Users\Ced\AppData\Local\Microsoft\WindowsApps;C:\Users\Ced\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\Ced\AppData\Roaming\npm;C:\Users\Ced\AppData\Local\Programs\mongosh\;C:\Program Files\MongoDB\Server\6.0\bin\
```

And even reinstalled Git Bash (PATH unchanged after)