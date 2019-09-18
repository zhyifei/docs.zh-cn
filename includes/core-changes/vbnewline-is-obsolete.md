---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988503"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="9feb9-101">Microsoft.VisualBasic.Constants.vbNewLine 已过时</span><span class="sxs-lookup"><span data-stu-id="9feb9-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="9feb9-102"><xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 常数在 .NET Framework 中被标记为[已过时](xref:System.ObsoleteAttribute)，但之前在 .net Core 3.0 库中缺少该属性。</span><span class="sxs-lookup"><span data-stu-id="9feb9-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) in .NET Framework, but the attribute was missing previously in the .NET Core 3.0 library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9feb9-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="9feb9-103">Version introduced</span></span>

<span data-ttu-id="9feb9-104">.NET Core 3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="9feb9-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="9feb9-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="9feb9-105">Details</span></span>

<span data-ttu-id="9feb9-106">从 .NET Core 3.0 预览版 8 开始，已将[已过时](xref:System.ObsoleteAttribute)属性应用于 <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 常数，使其符合 .NET Framework 中的 `vbNewLine`。</span><span class="sxs-lookup"><span data-stu-id="9feb9-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant to conform to `vbNewLine` in the .NET Framework.</span></span> <span data-ttu-id="9feb9-107">使用 `vbNewLine` 常量会生成编译器警告。</span><span class="sxs-lookup"><span data-stu-id="9feb9-107">Use of the `vbNewLine` constant produces a compiler warning.</span></span> 

<span data-ttu-id="9feb9-108">在早期版本的 .Net Core 中，`vbNewLine` 不会生成编译器警告。</span><span class="sxs-lookup"><span data-stu-id="9feb9-108">In previous versions of .NET Core, `vbNewLine` did not produce a compiler warning.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9feb9-109">建议的操作</span><span class="sxs-lookup"><span data-stu-id="9feb9-109">Recommended action</span></span>

<span data-ttu-id="9feb9-110">`vbNewLine` 的[已过时](xref:System.ObsoleteAttribute)属性消息包含以下建议：</span><span class="sxs-lookup"><span data-stu-id="9feb9-110">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="9feb9-111">对于回车符和换行符，请使用 [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf)。</span><span class="sxs-lookup"><span data-stu-id="9feb9-111">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="9feb9-112">对于当前平台的新行，请使用 <xref:System.Environment.NewLine?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="9feb9-112">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="9feb9-113">类别</span><span class="sxs-lookup"><span data-stu-id="9feb9-113">Category</span></span>

<span data-ttu-id="9feb9-114">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9feb9-114">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9feb9-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="9feb9-115">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

