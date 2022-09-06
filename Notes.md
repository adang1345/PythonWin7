## All Versions

- Build from a path that doesn't contain spaces. Otherwise, you may get an error 9009 when executing `gendef`.
- Set `PATCHDIR` to the location of a release downloaded from https://github.com/nalexandru/api-ms-win-core-path-HACK. This folder should contain `x86\api-ms-win-core-path-l1-1-0.dll` and `x64\api-ms-win-core-path-l1-1-0.dll`.

## Python 3.9

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll.patch`. Ignore whitespace warnings.
- Apply `enable-win7-install-1.patch` for 3.9.0-3.9.10 or `enable-win7-install-2.patch` for 3.9.11 or higher.
- Apply `libffi-fix-1.patch` for 3.9.0, `libffi-fix-2.patch` for 3.9.1, `libffi-fix-3.patch` for 3.9.2, `libffi-fix-4.patch` for 3.9.4, or `libffi-fix-5.patch` for 3.9.5-3.9.6 to avoid error where libffi-7.lib can't be found.
- Apply `guid-fix.patch` for 3.9.7 and higher to work around https://github.com/python/cpython/issues/96729.
- Apply `fix-htmlhelp.patch` for 3.9.0-3.9.10 to fix error in documentation build (https://bugs.python.org/issue46463).
- Apply `fix-chm.patch` to fix formatting errors in the `.chm` help file (https://bugs.python.org/issue47051).
- Run `buildrelease.bat -x86 -x64`.

## Python 3.10

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll.patch`. Ignore whitespace warnings.
- Apply `enable-win7-install-1.patch` for 3.10.0-3.10.2, `enable-win7-install-2.patch` for 3.10.3-3.10.7, or `enable-win7-install-3.patch` for 3.10.8 or higher.
- Apply `guid-fix.patch` for 3.10.0-3.10.7 to work around https://github.com/python/cpython/issues/96729.
- Apply `fix-htmlhelp.patch` for 3.10.0-3.10.2 to fix error in documentation build (https://bugs.python.org/issue46463).
- Apply `fix-chm.patch` for 3.10.0-3.10.6 to fix formatting errors in the `.chm` help file (https://bugs.python.org/issue47051).
- Run `buildrelease.bat -x86 -x64`.

## Python 3.11

- Install Sphinx 4.5.0 to a Python 3.9 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll.patch`. Ignore whitespace warnings.
- Apply `enable-win7-install-4.patch`.
- Apply `launcher-fix.patch` to revert changes to the Python launcher that are not compatible with Windows 7. This disables https://github.com/python/cpython/issues/90724 and related changes.
- Run `buildrelease.bat`.
