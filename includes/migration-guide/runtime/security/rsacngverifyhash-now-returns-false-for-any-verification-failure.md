---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887732"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="62d97-101">RSACng.VerifyHash 现在为任意验证失败返回 False</span><span class="sxs-lookup"><span data-stu-id="62d97-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="62d97-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="62d97-102">Details</span></span>|<span data-ttu-id="62d97-103">自 .NET Framework 4.6.2 起，如果签名本身格式不正确，则此方法返回 False  。</span><span class="sxs-lookup"><span data-stu-id="62d97-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="62d97-104">现在为任意验证失败返回 false。在 .NET Framework 4.6 和 4.6.1 中，如果签名格式错误，则此方法引发 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="62d97-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="62d97-105">建议</span><span class="sxs-lookup"><span data-stu-id="62d97-105">Suggestion</span></span>|<span data-ttu-id="62d97-106">如果验证失败且此方法返回 False  ，应改为执行依赖处理 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> 而实现执行的任意代码。</span><span class="sxs-lookup"><span data-stu-id="62d97-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns **False**.</span></span>|
|<span data-ttu-id="62d97-107">范围</span><span class="sxs-lookup"><span data-stu-id="62d97-107">Scope</span></span>|<span data-ttu-id="62d97-108">次要</span><span class="sxs-lookup"><span data-stu-id="62d97-108">Minor</span></span>|
|<span data-ttu-id="62d97-109">版本</span><span class="sxs-lookup"><span data-stu-id="62d97-109">Version</span></span>|<span data-ttu-id="62d97-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="62d97-110">4.6.2</span></span>|
|<span data-ttu-id="62d97-111">类型</span><span class="sxs-lookup"><span data-stu-id="62d97-111">Type</span></span>|<span data-ttu-id="62d97-112">运行时</span><span class="sxs-lookup"><span data-stu-id="62d97-112">Runtime</span></span>|
|<span data-ttu-id="62d97-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="62d97-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
