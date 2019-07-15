---
ms.openlocfilehash: 7d60578ac2913037e1cdeda329f06f9a4986574d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857576"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash 现在为任意验证失败返回 False

|   |   |
|---|---|
|详细信息|自 .NET Framework 4.6.2 起，如果签名本身格式不正确，则此方法返回 False。 现在为任意验证失败返回 false。在 .NET Framework 4.6 和 4.6.1 中，如果签名格式错误，则此方法引发 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>。|
|建议|如果验证失败且此方法返回 False，应改为执行依赖处理 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> 而实现执行的任意代码。|
|范围|次要|
|版本|4.6.2|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

