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
