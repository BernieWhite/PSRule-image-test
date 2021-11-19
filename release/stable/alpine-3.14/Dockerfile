# Copyright (c) Microsoft Corporation.
# Licensed under the MIT License.

ARG MODULE_VERSION=1.9.0

FROM mcr.microsoft.com/powershell:alpine-3.14
SHELL ["pwsh", "-Command"]
RUN $ProgressPreference = [System.Management.Automation.ActionPreference]::SilentlyContinue; \
    $Null = New-Item -Path /ps_modules/ -ItemType Directory -Force; \
    Save-Module -Name PSRule -RequiredVersion ${MODULE_VERSION} -Force -Path /ps_modules/;

COPY LICENSE powershell.ps1 /
CMD ["pwsh", "-File", "/powershell.ps1"]
