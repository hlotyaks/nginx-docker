# escape=`

FROM nginx
COPY static-html-directory /usr/share/nginx/html

## Use the latest Windows Server Core image with .NET Framework 4.8.
#FROM mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-ltsc2019
#
## Restore the default Windows shell for correct batch processing.
#SHELL ["cmd", "/S", "/C"]
#
## Copy install script. Collects vs install logs if install fails. Logs will be in c:\vslogs.zip
## COPY install.cmd C:\TEMP\
#
## Download collect.exe in case of an install failure.
## ADD https://aka.ms/vscollect.exe C:\TEMP\collect.exe
#
## Download vs buildtools
#ADD https://aka.ms/vs/17/release/vs_buildtools.exe c:\vs_buildtools.exe
#
## Install vs buildtools
#RUN `
#    start /w c:\vs_buildtools.exe --quiet --wait --norestart --nocache modify `
#     --installPath "%ProgramFiles(x86)%\Microsoft Visual Studio\2022\BuildTools" `
#     --channelUri C:\TEMP\VisualStudio.chman `
#     --installChannelUri C:\TEMP\VisualStudio.chman `
#     --add Microsoft.VisualStudio.Workload.VCTools `
#     --add Microsoft.VisualStudio.Workload.ManagedDesktopBuildTools `
#     --add Microsoft.VisualStudio.Workload.MSBuildTools `
#     --add Microsoft.VisualStudio.Component.VC.Tools.x86.x64 `
#     --add Microsoft.VisualStudio.Component.Windows10SDK.19041
#
## Collect the VS install logs. Find them in C:\%TEMP%
## RUN C:\TEMP\collect.exe -zip:C:\vslogs.zip
#
#COPY entrypointcommands.ps1 C:\scripts\entrypointcommands.ps1
#
#COPY msbuild.ps1 c:\scripts\msbuild.ps1
#
#WORKDIR /source
##
##RUN `
##    # Download the Build Tools bootstrapper.
##    curl -SL --output vs_buildtools.exe https://aka.ms/vs/17/release/vs_buildtools.exe `
##    `
##    # Install Build Tools with the Microsoft.VisualStudio.Workload.AzureBuildTools workload, excluding workloads and components with known issues.
##    && (start /w c:\TEMP\install.cmd vs_buildtools.exe --quiet --wait --norestart --nocache modify `
##        --installPath "%ProgramFiles(x86)%\Microsoft Visual Studio\2022\BuildTools" `
##        --channelUri C:\TEMP\VisualStudio.chman `
##        --installChannelUri C:\TEMP\VisualStudio.chman `
##        --add Microsoft.VisualStudio.Workload.VCTools `
##        --add Microsoft.VisualStudio.Workload.ManagedDesktopBuildTools `
##        --add Microsoft.VisualStudio.Workload.MSBuildTools) `
##    `
##    # Cleanup
##   && del /q vs_buildtools.exe
##
## Define the entry point for the docker container.
## This entry point starts the developer command prompt and launches the PowerShell shell.
##ENTRYPOINT ["C:\\Program Files (x86)\\Microsoft Visual Studio\\2022\\BuildTools\\Common7\\Tools\\VsDevCmd.bat", "&&", "powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
#
#ENTRYPOINT ["powershell.exe", "c:/scripts/entrypointcommands.ps1"]