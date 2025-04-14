## Python 3.9

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll-1.patch` for 3.9.0-3.9.12, `add-dll-2.patch` for 3.9.13-3.9.16, `add-dll-3.patch` for 3.9.17-3.9.18, or `add-dll-4.patch` for 3.9.19 or higher to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python executable.
- Apply `enable-win7-install-1.patch` for 3.9.0-3.9.10 or `enable-win7-install-2.patch` for 3.9.11 or higher to allow the installer to proceed on Windows 7 and to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `fix-libffi-1.patch` for 3.9.0, `fix-libffi-2.patch` for 3.9.1, `fix-libffi-3.patch` for 3.9.2, `fix-libffi-4.patch` for 3.9.4, or `fix-libffi-5.patch` for 3.9.5-3.9.6 to avoid error where `libffi-7.lib` can't be found (https://github.com/python/cpython/pull/27982).
- Apply `fix-guid.patch` for 3.9.7 and higher to work around https://github.com/python/cpython/issues/96729.
- Apply `fix-htmlhelp.patch` for 3.9.0-3.9.10 to fix error in documentation build (https://github.com/python/cpython/issues/90621).
- Apply `fix-chm.patch` to fix formatting errors in the `.chm` help file (https://github.com/python/cpython/issues/91207).
- Apply `support-vs-2022-1.patch` for 3.9.0-3.9.6, `support-vs-2022-2.patch` for 3.9.7-3.9.9, or `support-vs-2022-3.patch` for 3.9.10 or higher to support building with Visual Studio 2022 using the v143 toolset (derived from https://github.com/python/cpython/commit/d9301703fb1086cafbd730c17e3d450a192485d6 and https://github.com/python/cpython/commit/45faf151c693b6f13f78926761caea6df7242024).
- Apply `fix-vcruntime-threads-1.patch` to fix https://github.com/python/cpython/issues/115167.
- Run `buildrelease.bat -x86 -x64`.

## Python 3.10

- If you get an error during documentation build saying that `itircl.dll` was not registered correctly, go to `externals\windows-installer\htmlhelp` and run `regsvr32 itcc.dll`. Or you can install HTML Help Compiler system-wide, which would register this DLL anyway.
- Install Sphinx 3.5.4 to a Python 3.6 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll-1.patch` for 3.10.0-3.10.4 or `add-dll-2.patch` for 3.10.5-3.10.8, `add-dll-5.patch` for 3.10.9, `add-dll-6.patch` for 3.10.10-3.10.13, or `add-dll-4.patch` for 3.10.14 or higher to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python executable.
- Apply `enable-win7-install-1.patch` for 3.10.0-3.10.2, `enable-win7-install-2.patch` for 3.10.3-3.10.7, or `enable-win7-install-3.patch` for 3.10.8 or higher to allow the installer to proceed on Windows 7 and to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `fix-guid.patch` for 3.10.0-3.10.7 to work around https://github.com/python/cpython/issues/96729.
- Apply `fix-htmlhelp.patch` for 3.10.0-3.10.2 to fix error in documentation build (https://github.com/python/cpython/issues/90621).
- Apply `fix-chm.patch` for 3.10.0-3.10.6 to fix formatting errors in the `.chm` help file (https://github.com/python/cpython/issues/91207).
- Apply `support-vs-2022-4.patch` for 3.10.0, `support-vs-2022-5.patch` for 3.10.1-3.10.5, or `support-vs-2022-6.patch` for 3.10.6-3.10.10, or `support-vs-2022-7.patch` for 3.10.11 to support building with Visual Studio 2022 using the v143 toolset (derived from https://github.com/python/cpython/commit/d9301703fb1086cafbd730c17e3d450a192485d6 and https://github.com/python/cpython/commit/45faf151c693b6f13f78926761caea6df7242024).
- Apply `fix-vcruntime-threads-1.patch` to fix https://github.com/python/cpython/issues/115167.
- Run `buildrelease.bat -x86 -x64`.

## Python 3.11

- For 3.11.0-3.11.7, create a Python 3.9 venv. For 3.11.8 and higher, create a Python 3.10 venv. Set `PYTHON` to the location of the Python executable.
- Apply `fix-sphinx-dependencies.patch` for 3.11.0-3.11.7 to fix an error when building the documentation due to incompatible Sphinx dependencies (https://github.com/sphinx-doc/sphinx/issues/11890).
- Apply `add-dll-2.patch` for 3.11.0, `add-dll-5.patch` for 3.11.1, `add-dll-6.patch` for 3.11.2-3.11.7, or `add-dll-4.patch` for 3.11.8 or higher to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python executable.
- Apply `enable-win7-install-4.patch` for 3.11.0-3.11.3, `enable-win7-install-5.patch` for 3.11.4-3.11.8, or `enable-win7-install-6.patch` for 3.11.9 or higher to allow the installer to proceed on Windows 7 and to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `fix-launcher.patch` to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python launcher and to work around a bug in `RegGetValueW()` (https://stackoverflow.com/questions/47096940/reggetvalue-for-value-that-may-be-either-reg-sz-or-reg-expand-sz).
- Apply `fix-vcruntime-threads-1.patch` for 3.11.0-3.11.6 or `fix-vcruntime-threads-2.patch` for 3.11.7-3.11.8 to fix https://github.com/python/cpython/issues/115167.
- Run `buildrelease.bat`.

## Python 3.12

- Create a Python 3.11 venv and set `PYTHON` to the location of the Python executable. If building multiple versions in succession, create a fresh new venv with 3.12.0, 3.12.2, 3.12.4, 3.12.5, 3.12.6, 3.12.8, 3.12.9, and 3.12.10. Otherwise, the venv can be reused.
- Apply `fix-sphinx-dependencies.patch` for 3.12.0-3.12.1 to fix an error when building the documentation due to incompatible Sphinx dependencies (https://github.com/sphinx-doc/sphinx/issues/11890).
- Apply `add-dll-6.patch` for 3.12.0-3.12.1 or `add-dll-4.patch` for 3.12.2 or higher to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python executable.
- Apply `enable-win7-install-7.patch` for 3.12.0-3.12.2 or `enable-win7-install-8.patch` for 3.12.3 or higher to allow the installer to proceed on Windows 7 and to include debug symbols, debug binaries, and the Universal CRT in the installer.
- Apply `fix-launcher.patch` to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python launcher and to work around a bug in `RegGetValueW()` (https://stackoverflow.com/questions/47096940/reggetvalue-for-value-that-may-be-either-reg-sz-or-reg-expand-sz).
- Apply `restore-win7-handling-1.patch` to modify changes to the Python source code that are not compatible with Windows 7. This modifies https://github.com/python/cpython/commit/938e36f824c5f834d6b77d47942ad81edd5491d0 and https://github.com/python/cpython/commit/9ae49e3f3bdf585473f03522a1b7dd7c9e4baa6a.
- Apply `fix-os-fstat.patch` for 3.12.0 to fix https://github.com/python/cpython/issues/111856, which disproportionately affects Windows 7 compared to more recent Windows versions.
- Apply `fix-vcruntime-threads-1.patch` for 3.12.0 or `fix-vcruntime-threads-2.patch` for 3.12.1-3.12.2 to fix https://github.com/python/cpython/issues/115167.
- Apply `fix-sbom.patch` for 3.12.4-3.12.5 to fix error in SBOM generation (https://github.com/python/cpython/commit/db42934270c5c23be9f6804cad98dfd8234caf6f).
- Run `buildrelease.bat`.

## Python 3.13

- Create a Python 3.12 venv and set `PYTHON` to the location of the Python executable. If building multiple versions in succession, create a fresh new venv with 3.13.0, 3.13.1, 3.13.3, and 3.13.6. Otherwise, the venv can be reused.
- Apply `add-dll-7.patch` to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python executable.
- Apply `enable-win7-install-9.patch` to allow the installer to proceed on Windows 7 and to include debug symbols, debug binaries, the Universal CRT, and the experimental free-threaded build in the installer.
- Apply `fix-launcher.patch` to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python launcher and to work around a bug in `RegGetValueW()` (https://stackoverflow.com/questions/47096940/reggetvalue-for-value-that-may-be-either-reg-sz-or-reg-expand-sz).
- Apply `restore-win7-handling-2.patch` to modify changes to the Python source code that are not compatible with Windows 7. This modifies https://github.com/python/cpython/commit/938e36f824c5f834d6b77d47942ad81edd5491d0, https://github.com/python/cpython/commit/9ae49e3f3bdf585473f03522a1b7dd7c9e4baa6a, https://github.com/python/cpython/commit/be1c808fcad201adc4d5d6cca52ddb24aeb5e367, and https://github.com/python/cpython/commit/1d95451be1f3080904c00cc4c4a6cc519efdf321. This also modifies https://github.com/python/cpython/issues/111201 to avoid displaying a warning prior to Windows 10 TH2.
- Run `buildrelease.bat`.

## Python 3.14

- Create a Python 3.13 venv and set `PYTHON` to the location of the Python executable.
- Apply `add-dll-8.patch` to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python executable.
- Apply `enable-win7-install-10.patch` to allow the installer to proceed on Windows 7 and to include debug symbols, debug binaries, the Universal CRT, and the free-threaded build in the installer. Also remove the deprecation message from https://github.com/python/cpython/commit/e20ca6d1b006674be23d16083f273e8a7b8f77b6.
- Apply `fix-launcher.patch` to ensure that `api-ms-win-core-path-l1-1-0.dll` is installed next to the Python launcher and to work around a bug in `RegGetValueW()` (https://stackoverflow.com/questions/47096940/reggetvalue-for-value-that-may-be-either-reg-sz-or-reg-expand-sz).
- Apply `restore-win7-handling-3.patch` to modify changes to the Python source code that are not compatible with Windows 7. This modifies https://github.com/python/cpython/commit/938e36f824c5f834d6b77d47942ad81edd5491d0, https://github.com/python/cpython/commit/9ae49e3f3bdf585473f03522a1b7dd7c9e4baa6a, https://github.com/python/cpython/commit/be1c808fcad201adc4d5d6cca52ddb24aeb5e367, https://github.com/python/cpython/commit/1d95451be1f3080904c00cc4c4a6cc519efdf321, https://github.com/python/cpython/commit/d027787c8d89f59a9f0b1d7cc6972f5e16ffc740, and https://github.com/python/cpython/commit/014223649c33b2febbccfa221c2ab7f18a8c0847. This also modifies https://github.com/python/cpython/issues/111201 to avoid displaying a warning prior to Windows 10 TH2.
- Run `buildrelease.bat`.
