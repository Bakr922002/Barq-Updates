# Barq — Updates

This public repository carries only the version manifest for the Barq application.
The program source code is in a separate **private** repository.

## How updates work
Barq reads `latest.json` on startup. If its `version` is newer than the running copy,
an "Update available" mark appears in the program, and clicking it opens `url`.

## Releasing a new version
1. Raise the version in the program: `AssemblyInfo.cs`, `Barq.iss`, and `App/UpdateCheck.cs` are already wired; bump `AssemblyVersion` + `AssemblyFileVersion` and `AppVer` in `Barq.iss`.
2. Build: `publish-release.ps1` → produces `Barq-Setup.exe`.
3. Upload `Barq-Setup.exe` as the asset of a new Release here (tag = the version).
4. Raise `version` (and `notes`) in `latest.json` and commit.

Every running Barq then shows the update mark.
