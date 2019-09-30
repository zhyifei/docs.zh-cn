---
ms.openlocfilehash: 5ef785f476b795a9c53e511d51b2683b99e6da05
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181964"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="4d1a5-101">Microsoft.VisualBasic.Constants.vbNewLine 已过时</span><span class="sxs-lookup"><span data-stu-id="4d1a5-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="4d1a5-102">自 .NET Core 3.0 预览版 8 起，<xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 常量标记为[已过时](xref:System.ObsoleteAttribute)。</span><span class="sxs-lookup"><span data-stu-id="4d1a5-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) starting with .NET Core 3.0 Preview 8.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4d1a5-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="4d1a5-103">Version introduced</span></span>

<span data-ttu-id="4d1a5-104">.NET Core 3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="4d1a5-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="4d1a5-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="4d1a5-105">Details</span></span>

<span data-ttu-id="4d1a5-106">自 .NET Core 3.0 预览版 8 起，已向 <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 常量应用 [Obsolete](xref:System.ObsoleteAttribute) 属性。</span><span class="sxs-lookup"><span data-stu-id="4d1a5-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant.</span></span> <span data-ttu-id="4d1a5-107">使用常量会引发编辑器警告。</span><span class="sxs-lookup"><span data-stu-id="4d1a5-107">Use of the constant produces a compiler warning.</span></span> <span data-ttu-id="4d1a5-108">在之前的 .NET Core 和 .NET Framework 版本中，它未被标记为“已过时”。</span><span class="sxs-lookup"><span data-stu-id="4d1a5-108">In previous releases of both .NET Core and .NET Framework, it was not marked as obsolete.</span></span>

<span data-ttu-id="4d1a5-109">此项更改旨在支持将 Visual Basic 用作多平台开发的一种语言。</span><span class="sxs-lookup"><span data-stu-id="4d1a5-109">This change was made to support Visual Basic as a language for multi-platform development.</span></span> <span data-ttu-id="4d1a5-110">`vbNewLine` 常量与 Windows 上的换行符序列 `\r\n` 等效。</span><span class="sxs-lookup"><span data-stu-id="4d1a5-110">The `vbNewLine` constant is equivalent to `\r\n`, the newline character sequence on Windows.</span></span> <span data-ttu-id="4d1a5-111">在基于 Unix 的系统上，换行符为 `\n`。</span><span class="sxs-lookup"><span data-stu-id="4d1a5-111">On Unix-based systems, the newline character is `\n`.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="4d1a5-112">建议的操作</span><span class="sxs-lookup"><span data-stu-id="4d1a5-112">Recommended action</span></span>

<span data-ttu-id="4d1a5-113">`vbNewLine` 的[已过时](xref:System.ObsoleteAttribute)属性消息包含以下建议：</span><span class="sxs-lookup"><span data-stu-id="4d1a5-113">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="4d1a5-114">对于回车符和换行符，请使用 [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf)。</span><span class="sxs-lookup"><span data-stu-id="4d1a5-114">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="4d1a5-115">对于当前平台的新行，请使用 <xref:System.Environment.NewLine?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="4d1a5-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="4d1a5-116">类别</span><span class="sxs-lookup"><span data-stu-id="4d1a5-116">Category</span></span>

<span data-ttu-id="4d1a5-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d1a5-117">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4d1a5-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="4d1a5-118">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

