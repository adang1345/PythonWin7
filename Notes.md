## All Versions

- Build from a path that doesn't contain spaces. Otherwise, you may get an error 9009 when executing `gendef`.
- Set `PATCHDIR` to the location of a release downloaded from https://github.com/nalexandru/api-ms-win-core-path-HACK. This folder should contain `x86\api-ms-win-core-path-l1-1-0.dll` and `x64\api-ms-win-core-path-l1-1-0.dll`.

## Python 3.9

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll.patch`.
- Apply `enable-win7-install-1.patch` for 3.9.0-3.9.10 or `enable-win7-install-2.patch` for 3.9.11 or higher.
- Apply `fix-libffi-1.patch` for 3.9.0, `fix-libffi-2.patch` for 3.9.1, `fix-libffi-3.patch` for 3.9.2, `fix-libffi-4.patch` for 3.9.4, or `fix-libffi-5.patch` for 3.9.5-3.9.6 to avoid error where `libffi-7.lib` can't be found.
- Apply `fix-guid.patch` for 3.9.7 and higher to work around https://github.com/python/cpython/issues/96729.
- Apply `fix-htmlhelp.patch` for 3.9.0-3.9.10 to fix error in documentation build (https://github.com/python/cpython/issues/90621).
- Apply `fix-chm.patch` to fix formatting errors in the `.chm` help file (https://github.com/python/cpython/issues/91207).
- Run `buildrelease.bat -x86 -x64`.

## Python 3.10

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll.patch`.
- Apply `enable-win7-install-1.patch` for 3.10.0-3.10.2, `enable-win7-install-2.patch` for 3.10.3-3.10.7, or `enable-win7-install-3.patch` for 3.10.8 or higher.
- Apply `fix-guid.patch` for 3.10.0-3.10.7 to work around https://github.com/python/cpython/issues/96729.
- Apply `fix-htmlhelp.patch` for 3.10.0-3.10.2 to fix error in documentation build (https://github.com/python/cpython/issues/90621).
- Apply `fix-chm.patch` for 3.10.0-3.10.6 to fix formatting errors in the `.chm` help file (https://github.com/python/cpython/issues/91207).
- Apply `fix-pythonba.patch` for 3.10.11 to fix error building installer with Visual Studio 2022 (https://github.com/python/cpython/pull/103281).
- Run `buildrelease.bat -x86 -x64`.

## Python 3.11

- Install Sphinx 4.5.0 to a Python 3.9 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll.patch`.
- Apply `enable-win7-install-4.patch` for 3.11.0-3.11.3 or `enable-win7-install-5.patch` for 3.11.4 or higher.
- Apply `fix-launcher.patch` to revert changes to the Python launcher that are not compatible with Windows 7. This disables https://github.com/python/cpython/issues/90724 and related changes.
- Run `buildrelease.bat`.

## Python 3.12

- Install Sphinx 4.5.0 to a Python 3.11 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll.patch`.
- Apply `enable-win7-install-6.patch`.
- Apply `fix-launcher.patch` to revert changes to the Python launcher that are not compatible with Windows 7. This disables https://github.com/python/cpython/issues/90724 and related changes.
- Apply `restore-win7-handling.patch` to disable Python 3.12's use of features that are not available in Windows 7. This partially reverts https://github.com/python/cpython/commit/938e36f824c5f834d6b77d47942ad81edd5491d0 and modifies https://github.com/python/cpython/commit/9ae49e3f3bdf585473f03522a1b7dd7c9e4baa6a.
- Apply `fix-os-fstat.patch` for 3.12.0 to fix https://github.com/python/cpython/issues/111856, which disproportionately affects Windows 7 compared to more recent Windows versions.
- Run `buildrelease.bat`.
