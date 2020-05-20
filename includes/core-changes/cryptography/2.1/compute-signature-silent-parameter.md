---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449205"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a>已考虑 SignedCms.ComputeSignature 的布尔参数

在 .NET Core 中，已考虑 <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> 方法的布尔 `silent` 参数。 如果将此参数设置为 `true`，则不会显示 PIN 提示。

#### <a name="change-description"></a>更改描述

在 .NET Framework 中，<xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> 方法的 `silent` 参数将被忽略，并且如果提供程序要求，则始终会显示 PIN 提示。 在 .NET Core 中，已考虑 `silent` 参数，并且如果将其设置为 `true`，则即使提供程序要求也不会显示 PIN 提示。

在 2.1 版的 .NET Core 中引入了对 CMS/PKCS #7 消息的支持。

#### <a name="version-introduced"></a>引入的版本

2.1

#### <a name="recommended-action"></a>建议操作

为了确保在需要时显示 PIN 提示，桌面应用程序应调用 <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> 并将 Boolean 参数设置为 `false`。 无论是否禁用了静默上下文，所产生的行为都与 .NET Framework 上的行为相同。

### <a name="category"></a>类别

密码

### <a name="affected-apis"></a>受影响的 API

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
