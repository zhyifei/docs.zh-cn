---
ms.openlocfilehash: 480cbdecd681408a7e1d6fa366e3f1a4b131ab42
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857548"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="9f0a8-101">现在支持 Unicode 标准版本 8.0 类别</span><span class="sxs-lookup"><span data-stu-id="9f0a8-101">Unicode standard version 8.0 categories now supported</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9f0a8-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="9f0a8-102">Details</span></span>|<span data-ttu-id="9f0a8-103">在 .NET Framework 4.6.2 中，Unicode 数据已从 Unicode 标准版本 6.3 升级到版本 8.0。</span><span class="sxs-lookup"><span data-stu-id="9f0a8-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="9f0a8-104">在 .NET Framework 4.6.2 中请求 Unicode 字符类别时，某些结果可能与以前的 .NET Framework 版本中的结果不匹配。</span><span class="sxs-lookup"><span data-stu-id="9f0a8-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="9f0a8-105">此更改主要影响切罗基语音节和西双版纳新傣文元音标记和音调标记。</span><span class="sxs-lookup"><span data-stu-id="9f0a8-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>|
|<span data-ttu-id="9f0a8-106">建议</span><span class="sxs-lookup"><span data-stu-id="9f0a8-106">Suggestion</span></span>|<span data-ttu-id="9f0a8-107">检查代码并删除/更改依赖硬编码 Unicode 字符类别的逻辑。</span><span class="sxs-lookup"><span data-stu-id="9f0a8-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>|
|<span data-ttu-id="9f0a8-108">范围</span><span class="sxs-lookup"><span data-stu-id="9f0a8-108">Scope</span></span>|<span data-ttu-id="9f0a8-109">次要</span><span class="sxs-lookup"><span data-stu-id="9f0a8-109">Minor</span></span>|
|<span data-ttu-id="9f0a8-110">版本</span><span class="sxs-lookup"><span data-stu-id="9f0a8-110">Version</span></span>|<span data-ttu-id="9f0a8-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="9f0a8-111">4.6.2</span></span>|
|<span data-ttu-id="9f0a8-112">类型</span><span class="sxs-lookup"><span data-stu-id="9f0a8-112">Type</span></span>|<span data-ttu-id="9f0a8-113">运行时</span><span class="sxs-lookup"><span data-stu-id="9f0a8-113">Runtime</span></span>|
|<span data-ttu-id="9f0a8-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="9f0a8-114">Affected APIs</span></span>|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|

