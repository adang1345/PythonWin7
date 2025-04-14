## 14 October 2025

- Add 3.13.9.

## 10 October 2025

- Add 3.9.24, 3.10.19, 3.11.14, and 3.12.12.

## 7 October 2025

- Add 3.13.8.
- Replace 3.14.0rc3 with 3.14.0.

## 25 September 2025

- Rebuild all packages to support Windows Vista SP2 and Windows Server 2008 SP2.
- Add 3.8, which does not officially support Windows Vista SP2 and Windows Server 2008 SP2.
- Rename the repository from PythonWin7 to PythonVista.
- Fix an error installing the Universal C Runtime (https://github.com/python/cpython/issues/138896) for versions that are affected by the bug.
- Clean up the `enable-win7-install` patch files by splitting them into `build-full-installer` and `restore-vista-handling` patch files.
- Replace 3.14.0rc2 with 3.14.0rc3.

## 4 September 2025

- Rebuild all packages to correct the version of Visual Studio required to use the debug symbols and debug binaries.
- Remove `index` line from patch files. These are unnecessary.
- Update `README.md` and `Notes.md` to stop labeling the free-threaded build as experimental for Python 3.14.

## 20 August 2025

- Remove note to build from a path that does not contain spaces due to an error when executing `gendef`. This is no longer required in Python 3.9+ due to https://github.com/python/cpython/commit/f5690925df897cf45818bf944b28d13f37b9f8ca.

## 19 August 2025

- Rebuild all packages to use https://github.com/adang1345/api-ms-win-core-path instead of https://github.com/nalexandru/api-ms-win-core-path-HACK. Use the Visual Studio 2022 toolset for all builds.
- Add 3.13.7.
- Replace 3.14.0rc1 with 3.14.0rc2.

## Previous

- Project was first published on 6 September 2022 due to a request at https://github.com/adang1345/PythonWindows/issues/8. This project's history was not recorded until 19 August 2025.
