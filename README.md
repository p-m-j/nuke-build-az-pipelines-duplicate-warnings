# Bug report reproduction steps

```bash
$ export TF_BUILD=1
$ ./build.sh
```

```pwsh
PS> $env:TF_BUILD=1
PS> ./build.ps1
```

Note logging commands for the single warning appear in both the warnings and the summary sections.

e.g.

```
PowerShell Core version 7.3.8
Microsoft (R) .NET SDK version 7.0.102
​
███╗   ██╗██╗   ██╗██╗  ██╗███████╗
████╗  ██║██║   ██║██║ ██╔╝██╔════╝
██╔██╗ ██║██║   ██║█████╔╝ █████╗  
██║╚██╗██║██║   ██║██╔═██╗ ██╔══╝  
██║ ╚████║╚██████╔╝██║  ██╗███████╗
╚═╝  ╚═══╝ ╚═════╝ ╚═╝  ╚═╝╚══════╝
​
NUKE Execution Engine version 7.0.6 (Windows,.NETCoreApp,Version=v6.0)
​
##[group]Compile
19:59:10 [INF] > "C:\Program Files\dotnet\dotnet.exe" build C:\Users\pmj\Dev\nuke-build-duplicate-warnings\demo.sln --no-incremental
19:59:10 [DBG] MSBuild version 17.4.1+9a89d02ff for .NET
19:59:11 [DBG]   Determining projects to restore...
19:59:11 [DBG]   All projects are up-to-date for restore.
##vso[task.logissue type=warning]C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Class1.cs(5,19): warning CS8618: Non-nullable property 'Foo' must contain a non-null value when exiting constructor. Consider declaring the property as nullable. [C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Demo.Library.csproj]
19:59:12 [WRN] C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Class1.cs(5,19): warning CS8618: Non-nullable property 'Foo' must contain a non-null value when exiting constructor. Consider declaring the property as nullable. [C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Demo.Library.csproj]
19:59:12 [DBG]   Demo.Library -> C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\bin\Debug\net7.0\Demo.Library.dll
19:59:12 [DBG]
19:59:12 [DBG] Build succeeded.
19:59:12 [DBG]
##vso[task.logissue type=warning]C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Class1.cs(5,19): warning CS8618: Non-nullable property 'Foo' must contain a non-null value when exiting constructor. Consider declaring the property as nullable. [C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Demo.Library.csproj]
19:59:12 [WRN] C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Class1.cs(5,19): warning CS8618: Non-nullable property 'Foo' must contain a non-null value when exiting constructor. Consider declaring the property as nullable. [C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Demo.Library.csproj]
19:59:12 [DBG]     1 Warning(s)
19:59:12 [DBG]     0 Error(s)
19:59:12 [DBG]
19:59:12 [DBG] Time Elapsed 00:00:01.73
##[endgroup]Compile
##[group]Errors & Warnings
[WRN] Compile: C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Class1.cs(5,19): warning CS8618: Non-nullable property 'Foo' must contain a non-null value when exiting constructor. Consider declaring the property as nullable. [C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Demo.Library.csproj]
[WRN] Compile: C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Class1.cs(5,19): warning CS8618: Non-nullable property 'Foo' must contain a non-null value when exiting constructor. Consider declaring the property as nullable. [C:\Users\pmj\Dev\nuke-build-duplicate-warnings\Demo.Library\Demo.Library.csproj]
##[endgroup]Errors & Warnings
​
═══════════════════════════════════════
Target             Status      Duration
───────────────────────────────────────
Compile            Succeeded       0:01
───────────────────────────────────────
Total                              0:01
═══════════════════════════════════════
​
Build succeeded on 18/10/2023 19:59:12. ＼（＾ᴗ＾）／
```
