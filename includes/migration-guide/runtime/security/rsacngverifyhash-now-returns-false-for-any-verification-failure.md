---
ms.openlocfilehash: acf4e8df2cef3d9ec5d123a14cc7bfcd6f1bfb8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235987"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="413bd-101">RSACng.VerifyHash 现在为任意验证失败返回 False</span><span class="sxs-lookup"><span data-stu-id="413bd-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="413bd-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="413bd-102">Details</span></span>|<span data-ttu-id="413bd-103">自 .NET Framework 4.6.2 起，如果签名本身格式不正确，则此方法返回 False。</span><span class="sxs-lookup"><span data-stu-id="413bd-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="413bd-104">现在为任意验证失败返回 false。在 .NET Framework 4.6 和 4.6.1 中，如果签名格式错误，则此方法引发 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="413bd-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="413bd-105">建议</span><span class="sxs-lookup"><span data-stu-id="413bd-105">Suggestion</span></span>|<span data-ttu-id="413bd-106">如果验证失败且此方法返回 False，应改为执行依赖处理 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> 而实现执行的任意代码。</span><span class="sxs-lookup"><span data-stu-id="413bd-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="413bd-107">范围</span><span class="sxs-lookup"><span data-stu-id="413bd-107">Scope</span></span>|<span data-ttu-id="413bd-108">次要</span><span class="sxs-lookup"><span data-stu-id="413bd-108">Minor</span></span>|
|<span data-ttu-id="413bd-109">版本</span><span class="sxs-lookup"><span data-stu-id="413bd-109">Version</span></span>|<span data-ttu-id="413bd-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="413bd-110">4.6.2</span></span>|
|<span data-ttu-id="413bd-111">类型</span><span class="sxs-lookup"><span data-stu-id="413bd-111">Type</span></span>|<span data-ttu-id="413bd-112">运行时</span><span class="sxs-lookup"><span data-stu-id="413bd-112">Runtime</span></span>|
|<span data-ttu-id="413bd-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="413bd-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
