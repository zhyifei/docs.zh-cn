---
ms.openlocfilehash: d61e4da187b3ede5e49fa80903d6e4c3b40578b9
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216275"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="cf632-101">Microsoft.VisualBasic.MyServices 命名空间中的类型不可用</span><span class="sxs-lookup"><span data-stu-id="cf632-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="cf632-102"><xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 命名空间中的类型不可用。</span><span class="sxs-lookup"><span data-stu-id="cf632-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cf632-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="cf632-103">Version introduced</span></span>

<span data-ttu-id="cf632-104">.NET Core 3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="cf632-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="cf632-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="cf632-105">Details</span></span>

<span data-ttu-id="cf632-106"><xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 中的类型之前在某些 .NET Core 3.0 预览版本中可用。</span><span class="sxs-lookup"><span data-stu-id="cf632-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="cf632-107">自 NET Core 3.0 预览版 9 起，它们不再可用。</span><span class="sxs-lookup"><span data-stu-id="cf632-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="cf632-108">已删除这些类型，以避免在后续版本中出现不必要的程序集依赖项或中断性变更。</span><span class="sxs-lookup"><span data-stu-id="cf632-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="cf632-109">建议的操作</span><span class="sxs-lookup"><span data-stu-id="cf632-109">Recommended action</span></span>

<span data-ttu-id="cf632-110">如果你的代码依赖于对 Microsoft.VisualBasic.MyServices 类型及其成员的使用，可使用 .NET 类库中的相应类型和成员  。</span><span class="sxs-lookup"><span data-stu-id="cf632-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="cf632-111">下面是 Microsoft.VisualBasic.MyServices 到其等效 .NET 类库类型的映射  ：</span><span class="sxs-lookup"><span data-stu-id="cf632-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="cf632-112">Microsoft.VisualBasic.MyServices 类型</span><span class="sxs-lookup"><span data-stu-id="cf632-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="cf632-113">.NET 类库类型</span><span class="sxs-lookup"><span data-stu-id="cf632-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="cf632-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> 用于 WPF 应用程序，<xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> 用于 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="cf632-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>| 
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="cf632-115"><xref:System.IO> 命名空间中的类型</span><span class="sxs-lookup"><span data-stu-id="cf632-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="cf632-116"><xref:Microsoft.Win32> 命名空间中与注册表相关的类型</span><span class="sxs-lookup"><span data-stu-id="cf632-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="cf632-117">类别</span><span class="sxs-lookup"><span data-stu-id="cf632-117">Category</span></span>

<span data-ttu-id="cf632-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf632-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cf632-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="cf632-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

