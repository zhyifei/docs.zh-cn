---
ms.openlocfilehash: 69b25db88c7580787bbb47fb0902b6bb072f8dde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235203"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="87b59-101">使用 Regex.CompileToAssembly 进行编译的程序集在 4.0 和 4.5 之间中断</span><span class="sxs-lookup"><span data-stu-id="87b59-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

|   |   |
|---|---|
|<span data-ttu-id="87b59-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="87b59-102">Details</span></span>|<span data-ttu-id="87b59-103">如果已编译的正则表达式的程序集使用 .NET Framework 4.5 生成但却面向 .NET Framework 4，则在安装了 .NET Framework 4 的系统上尝试使用该程序集的正则表达式之一时，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="87b59-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>|
|<span data-ttu-id="87b59-104">建议</span><span class="sxs-lookup"><span data-stu-id="87b59-104">Suggestion</span></span>|<span data-ttu-id="87b59-105">若要解决此问题，可执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="87b59-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="87b59-106">使用 .NET Framework 4 生成包含正则表达式的程序集。</span><span class="sxs-lookup"><span data-stu-id="87b59-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="87b59-107">使用已解释的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="87b59-107">Use an interpreted regular expression.</span></span></li></ul>|
|<span data-ttu-id="87b59-108">范围</span><span class="sxs-lookup"><span data-stu-id="87b59-108">Scope</span></span>|<span data-ttu-id="87b59-109">次要</span><span class="sxs-lookup"><span data-stu-id="87b59-109">Minor</span></span>|
|<span data-ttu-id="87b59-110">版本</span><span class="sxs-lookup"><span data-stu-id="87b59-110">Version</span></span>|<span data-ttu-id="87b59-111">4.5</span><span class="sxs-lookup"><span data-stu-id="87b59-111">4.5</span></span>|
|<span data-ttu-id="87b59-112">类型</span><span class="sxs-lookup"><span data-stu-id="87b59-112">Type</span></span>|<span data-ttu-id="87b59-113">运行时</span><span class="sxs-lookup"><span data-stu-id="87b59-113">Runtime</span></span>|
|<span data-ttu-id="87b59-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="87b59-114">Affected APIs</span></span>|<ul><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
