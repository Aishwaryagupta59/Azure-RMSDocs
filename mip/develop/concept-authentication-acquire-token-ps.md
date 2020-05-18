---
title: Concepts - Using PowerShell to acquire an access token.
description: This article will help you understand how to use PowerShell to acquire an OAuth2 access token. This is required by the implementation of the authentication delegate.
author: msmbaldwin
ms.service: information-protection
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: mbaldwin
ms.custom: has-adal-ref
---

# Acquire an access token (PowerShell)

The example shown demonstrates how to call an external PowerShell script to obtain an OAuth2 token. A valid OAuth2 access token is required by the implementation of the authentication delegate.

## Prerequisites

- Complete [(MIP) SDK setup and configuration](setup-configure-mip.md). Among other tasks, you'll register your client application in your Azure Active Directory (Azure AD) tenant. Azure AD will provide an application ID, also known as client ID, which is used in your token acquisition logic.

This code isn't intended for production use. It may only be used for development and understanding auth concepts.

## sample::auth::AcquireToken()

### auth.h

We create a single function called AcquireToken. Since the return value will be hard-coded for this tutorial, we accept no parameters and return a string (the token).

```cpp
//auth.h
#include <string>

namespace sample {
  namespace auth {
    std::string AcquireToken();
  }
}
```

### auth.cpp

Our source file returns a token value that will be hard-coded in a future step.

```cpp
//auth.cpp
#include <string>
#include "auth.h"

namespace sample {
  namespace auth {
    string AcquireToken() {
      std::string mToken = "your token here";
      return mToken;
    }
  }
}
```

## Mint a token

Finally, mint a token to put in the mToken variable. The example below demonstrates a PowerShell script that can be used to quickly obtain the OAuth2 token via ADAL and PowerShell on Windows. This token is granted for the Office 365 Security and Compliance Center endpoint only. Consequently, protection actions will fail unless the resource URL is updated.

### Install [ADAL.PS](https://www.powershellgallery.com/packages/ADAL.PS/3.19.4.2) from PS Gallery

You can skip this step if you completed it previously in [(MIP) SDK setup and configuration](setup-configure-mip.md).

```PowerShell
Install-Module -Name ADAL.PS
```

### Use Get-ADALToken to Obtain the Access Token

```PowerShell
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/common/oauth2/authorize"
#this is the security and compliance center endpoint
$resourceUrl = "https://syncservice.o365syncservice.com/"
#replace <application-id> and <redirect-uri>, with the Redirect URI and Application ID from your Azure AD application registration.
$clientId = "<application-id>"
$redirectUri = "<redirect-uri>"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
```

Copy the token from the clipboard in to auth.cpp as the value for `string mToken`, replacing "your token here" above. Running the script again may be required, depending on how long the following steps take.
