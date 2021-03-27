# Microsoft.Build.Artifacts Issue

The purpose of this repository is to demonstrate a problem with using [Microsoft.Build.Artifacts](https://github.com/microsoft/MSBuildSdks/tree/master/src/Artifacts) on Linux.
The issue is captured at [Microsoft.Build.Artifacts not working on Linux](https://github.com/microsoft/MSBuildSdks/issues/233).

## Reproducing the Problem

On a machine with the [.NET 5 SDK](https://dotnet.microsoft.com/download/dotnet/5.0) installed, clone the repository and build the project:

```bash
dotnet build --configuration Release
```

On Windows 10, building will generate an **artifacts** folder in the repository root that contains **ArtifactsIssue.1.0.0.nupkg**.
On Linux (tested on Ubuntu 20.04 LTS running on Windows 10 via WSL 2), executing the same command builds the project but does not create an **artifacts** folder and copy the NuGet package into it.

To clean up the folders between build attempts, run this:

```bash
git clean -fxd
```
