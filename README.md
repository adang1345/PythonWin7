# Unofficial Python Installers for Windows Vista SP2 and Windows Server 2008 SP2

Officially, Python 3.8 and above are not supported on Windows Vista SP2 and Windows Server 2008 SP2. Here, you can obtain unofficial Windows installers that bring back support for these older Windows versions.

These installers also work on newer versions of Windows and can be used whenever official support is dropped.

*Note:* On Windows Vista SP2, Windows Server 2008 SP2, Windows 7 SP1, and Windows Server 2008 R2 SP1, update KB2533623 must be installed for Python to run. Ensure that your computer is up-to-date via Windows Update. Alternatively, you can manually install update KB3063858, which supersedes KB2533623. Update KB3063858 can be obtained at the following links.
- [Windows Vista SP2 x86](https://download.microsoft.com/download/8/B/F/8BF76ABD-2A61-470A-BE45-84700728286D/Windows6.0-KB3063858-x86.msu)
- [Windows Vista SP2 x64](https://download.microsoft.com/download/B/4/0/B404246A-46B3-448D-A9F1-E703C7261801/Windows6.0-KB3063858-x64.msu)
- [Windows Server 2008 SP2 x86](https://download.microsoft.com/download/A/D/9/AD9044CE-2569-4963-91BF-5ABA7CC9DB09/Windows6.0-KB3063858-x86.msu)
- [Windows Server 2008 SP2 x64](https://download.microsoft.com/download/C/E/6/CE6BBF49-4D23-4FAC-A80C-41FC06B7D3EE/Windows6.0-KB3063858-x64.msu)
- [Windows 7 SP1 x86](https://download.microsoft.com/download/C/9/6/C96CD606-3E05-4E1C-B201-51211AE80B1E/Windows6.1-KB3063858-x86.msu)
- [Windows 7 SP1 x64](https://download.microsoft.com/download/0/8/E/08E0386B-F6AF-4651-8D1B-C0A95D2731F0/Windows6.1-KB3063858-x64.msu)
- [Windows Server 2008 R2 SP1 x64](https://download.microsoft.com/download/D/0/7/D0757054-F917-4728-935B-200AEAFE0308/Windows6.1-KB3063858-x64.msu)

For each Python version, this repository includes the following.
- 64-bit executable installer (e.g. python-3.8.0-amd64-full.exe)
- 32-bit executable installer (e.g. python-3.8.0-full.exe)
- 64-bit embeddable zip file (e.g. python-3.8.0-embed-amd64.zip)
- 32-bit embeddable zip file (e.g. python-3.8.0-embed-win32.zip)
- 64-bit NuGet package (e.g. python.3.8.0.nupkg)
- 32-bit NuGet package (e.g. pythonx86.3.8.0.nupkg)
- 64-bit free-threaded NuGet package (e.g. python-freethreaded.3.13.0.nupkg) (since 3.13)
- 32-bit free-threaded NuGet package (e.g. pythonx86-freethreaded.3.13.0.nupkg) (since 3.13)
- Windows help file (e.g. python380.chm) (3.8-3.10 only)

For the more technical among you, these installers were built from the source distributions published at https://www.python.org/downloads/source/, with the following modifications.
- Edit the OS version check to allow the installer to proceed on Windows Vista SP2 and Windows Server 2008 SP2.
- For Python 3.9+, include the file `api-ms-win-core-path-l1-1-0.dll` in the distribution. This file was obtained from https://github.com/adang1345/api-ms-win-core-path and is necessary for Python to run on older Windows versions.
- Create full installers that include all components to allow for a fully offline installation. These include debug symbols, debug binaries, and the Universal CRT. For Python 3.13+, these include the free-threaded build as well.
- Modify the Python source code to restore compatibility with Windows Vista SP2 and Windows Server 2008 SP2. At runtime, check whether a possibly unsupported Windows API function exists on the current system and use an alternative if it does not. Work around bugs in Windows API functions that exist on older versions of Windows.
- Fix a few bugs in the build scripts.

See [Notes.md](Notes.md) for more specific details about how I built these installers and how you may build them yourself.

## NuGet Packages

To install a `.nupkg` package, ensure that you have the [NuGet Command-Line Interface](https://learn.microsoft.com/en-us/nuget/reference/nuget-exe-cli-reference?tabs=windows) installed. Go to the directory containing the `.nupkg` file. Replace `target\installation\directory` in the following commands with the desired location to install the package.

### Command Prompt
For 64-bit Python, run `nuget install python -Source %cd% -OutputDirectory target\installation\directory`

For 32-bit Python, run `nuget install pythonx86 -Source %cd% -OutputDirectory target\installation\directory`

### PowerShell
For 64-bit Python, run `nuget install python -Source $(Get-Location) -OutputDirectory target\installation\directory`

For 32-bit Python, run `nuget install pythonx86 -Source $(Get-Location) -OutputDirectory target\installation\directory`

## Git History

In an effort to keep the size of this repository low, the Git history will not be kept. Updates will be made via force-pushes. If you fork this repository and wish to update your fork, see https://stackoverflow.com/questions/9646167/clean-up-a-fork-and-restart-it-from-the-upstream.

The project history is recorded at [CHANGELOG.md](CHANGELOG.md).

## License

These files are provided under the MIT License. See [LICENSE.txt](LICENSE.txt).

## Who am I

I am Aohan Dang (https://www.linkedin.com/in/aohan-dang-536643a7/), a professional software developer and Python enthusiast.
