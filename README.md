# Unofficial Python Installers for Windows 7 SP1 and Windows Server 2008 R2

Officially, Python 3.9 and above are not supported on Windows 7 SP1 and Windows Server 2008 R2. Here, you can obtain unofficial Windows installers that bring back support for these older Windows versions.

*Note:* Windows update KB2533623 must be installed for Python to run. Ensure that your computer is up-to-date via Windows Update. Alternatively, click [here](https://www.microsoft.com/en-us/download/details.aspx?id=47409) to manually install update KB3063858, which supersedes KB2533623.

For each Python version, this repository includes the following.
- 64-bit executable installer (e.g. python-3.9.0-amd64-full.exe)
- 32-bit executable installer (e.g. python-3.9.0-full.exe)
- 64-bit embeddable zip file (e.g. python-3.9.0-embed-amd64.zip)
- 32-bit embeddable zip file (e.g. python-3.9.0-embed-win32.zip)
- 64-bit NuGet package (e.g. python.3.9.0.nupkg)
- 32-bit NuGet package (e.g. pythonx86.3.9.0.nupkg)
- Windows help file (e.g. python390.chm) (3.9 and 3.10 only)

For the more technical among you, these installers were built from the source distributions published at https://www.python.org/downloads/source/, with the following modifications.
- Include the file `api-ms-win-core-path-l1-1-0.dll` in the distribution. This file was obtained from https://github.com/nalexandru/api-ms-win-core-path-HACK and is necessary for Python to run on older Windows versions.
- Create full installers that include debugging symbols and debug binaries without needing to download them.
- Allow the installer to proceed on Windows 7 SP1 and Windows Server 2008 R2.
- For Python 3.11 or higher, remove the usage of features that are not available on Windows 7.
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

### Example of using it in a GitHub workflow (to build Win7 compatible standalone programs)
```yaml
name: Build and publish

env:
  PY_PATH:

on:
  repository_dispatch:

jobs:
  windows-build:
    name: Windows
    runs-on: windows-latest

    steps:
      - name: Checkout source
        uses: actions/checkout@v4

      - name: Set up Python
        run: |
          Invoke-WebRequest -Uri "https://github.com/adang1345/PythonWin7/raw/master/3.12.1/python.3.12.1.nupkg" -OutFile "python.3.12.1.nupkg"
          mkdir "C:\pywin7"
          nuget install python -Source $(Get-Location) -OutputDirectory "C:\pywin7\"
          echo "C:\pywin7\python.3.12.1\tools" | Out-File -FilePath $env:GITHUB_PATH -Encoding utf8 -Append

      - name: Set up libraries
        run: |
          python -m pip install PyInstaller # or "https://github.com/pcroland/Pyinstaller-Builds/releases/download/PyInstaller/pyinstaller-6.3.0-py3-none-win_amd64.whl" for less false positive virus flagging
          python -m pip install .

      - name: Build
        run: |
          python -m PyInstaller -F __main__.py -n [program name here] --icon [logo_path]
```

## Git History

In an effort to keep the size of this repository low, the Git history will not be kept. All updates will be made via force-pushes. If you fork this repository and wish to update your fork, see https://stackoverflow.com/questions/9646167/clean-up-a-fork-and-restart-it-from-the-upstream.

## License

These files are provided under the MIT License. See [LICENSE.txt](LICENSE.txt).

## Who am I

I am Aohan Dang (https://www.linkedin.com/in/aohan-dang-536643a7/), a professional software developer and Python enthusiast.
