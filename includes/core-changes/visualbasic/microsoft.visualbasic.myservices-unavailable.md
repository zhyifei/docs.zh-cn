---
ms.openlocfilehash: 58e65bae1593f23945a971b896a1db4a929b4587
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198351"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="386d6-101">Microsoft.VisualBasic.MyServices 命名空间中的类型不可用</span><span class="sxs-lookup"><span data-stu-id="386d6-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="386d6-102"><xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 命名空间中的类型不可用。</span><span class="sxs-lookup"><span data-stu-id="386d6-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="386d6-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="386d6-103">Version introduced</span></span>

<span data-ttu-id="386d6-104">.NET Core 3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="386d6-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="386d6-105">更改描述</span><span class="sxs-lookup"><span data-stu-id="386d6-105">Change description</span></span>

<span data-ttu-id="386d6-106"><xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 中的类型之前在某些 .NET Core 3.0 预览版本中可用。</span><span class="sxs-lookup"><span data-stu-id="386d6-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="386d6-107">自 NET Core 3.0 预览版 9 起，它们不再可用。</span><span class="sxs-lookup"><span data-stu-id="386d6-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="386d6-108">已删除这些类型，以避免在后续版本中出现不必要的程序集依赖项或中断性变更。</span><span class="sxs-lookup"><span data-stu-id="386d6-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="386d6-109">建议的操作</span><span class="sxs-lookup"><span data-stu-id="386d6-109">Recommended action</span></span>

<span data-ttu-id="386d6-110">如果你的代码依赖于对 Microsoft.VisualBasic.MyServices 类型及其成员的使用，可使用 .NET 类库中的相应类型和成员  。</span><span class="sxs-lookup"><span data-stu-id="386d6-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="386d6-111">下面是 Microsoft.VisualBasic.MyServices 到其等效 .NET 类库类型的映射  ：</span><span class="sxs-lookup"><span data-stu-id="386d6-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="386d6-112">Microsoft.VisualBasic.MyServices 类型</span><span class="sxs-lookup"><span data-stu-id="386d6-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="386d6-113">.NET 类库类型</span><span class="sxs-lookup"><span data-stu-id="386d6-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="386d6-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> 用于 WPF 应用程序，<xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> 用于 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="386d6-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="386d6-115"><xref:System.IO> 命名空间中的类型</span><span class="sxs-lookup"><span data-stu-id="386d6-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="386d6-116"><xref:Microsoft.Win32> 命名空间中与注册表相关的类型</span><span class="sxs-lookup"><span data-stu-id="386d6-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="386d6-117">类别</span><span class="sxs-lookup"><span data-stu-id="386d6-117">Category</span></span>

<span data-ttu-id="386d6-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="386d6-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="386d6-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="386d6-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

