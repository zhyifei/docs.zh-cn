---
ms.openlocfilehash: 07ab65de16b72bd0844a39e4b35235c5f043f3ec
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117264"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a>RSAOpenSsl 密钥生成的最小大小已增加

在 Linux 上生成新 RSA 密钥的最小大小已从 384 位提高到 512 位。

#### <a name="change-description"></a>更改描述

从 .NET Core 3.0 开始，由 Linux 的 <System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>、<System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType> 和 <System.Security.Cryptography.RSACryptoServicePlatform.%23ctor%2A?displayProperty=nameWithType> 中的 RSA 实例上的 `LegalKeySizes` 属性报告的最小合法密钥大小已从 384 提高到 512。

因此，在 .NET Core 2.2 及更早版本中，方法调用（如 `RSA.Create(384)`）会成功。 在 .NET Core 3.0 及更高版本中，方法调用 `RSA.Create(384)` 会引发异常，指示大小太小。

此更改是因为在 Linux 上执行加密操作的 OpenSSL 在版本 1.0.2 和 1.1.0 之间提高了其最小值。  .NET Core 3.0 倾向于使用 OpenSSL 1.1.x 而不是 1.0.x，并提高了最小报告版本来反映这一新的更高的依赖项限制。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="recommended-action"></a>建议的操作

如果调用任何受影响的 API，请确保所有生成的密钥的大小不小于提供程序的最小值。

> [!NOTE]
> 384 位 RSA 已被视为不安全（512 位 RSA 也是如此）。 新式建议（例如 [NIST 特别出版物 800-57 第 1 部分修订版 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)）建议将 2048 位作为新生成的密钥的最小大小。

#### <a name="category"></a>类别

密码

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`


-->
