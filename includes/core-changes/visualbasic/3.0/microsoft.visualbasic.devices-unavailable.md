---
ms.openlocfilehash: 4c47b95e98aca727d9f0eda54a167a71fd53afb9
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567458"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="a0066-101">Microsoft.VisualBasic.Devices 命名空间中的类型不可用</span><span class="sxs-lookup"><span data-stu-id="a0066-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="a0066-102"><xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 命名空间中的类型不可用。</span><span class="sxs-lookup"><span data-stu-id="a0066-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a0066-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="a0066-103">Version introduced</span></span>

<span data-ttu-id="a0066-104">.NET Core 3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="a0066-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="a0066-105">更改描述</span><span class="sxs-lookup"><span data-stu-id="a0066-105">Change description</span></span>

<span data-ttu-id="a0066-106"><xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 中的类型之前在某些 .NET Core 3.0 预览版本中可用。</span><span class="sxs-lookup"><span data-stu-id="a0066-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="a0066-107">自 NET Core 3.0 预览版 9 起，它们不再可用。</span><span class="sxs-lookup"><span data-stu-id="a0066-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="a0066-108">已删除这些类型，以避免在后续版本中出现不必要的程序集依赖项或中断性变更。</span><span class="sxs-lookup"><span data-stu-id="a0066-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a0066-109">建议的操作</span><span class="sxs-lookup"><span data-stu-id="a0066-109">Recommended action</span></span>

<span data-ttu-id="a0066-110">如果你的代码依赖于对 <xref:Microsoft.VisualBasic.Devices> 类型及其成员的使用，可使用 .NET 类库中的相应类型或成员。</span><span class="sxs-lookup"><span data-stu-id="a0066-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="a0066-111">例如，<xref:System.DateTime?displayProperty=nameWithType> 和 <xref:System.Environment?displayProperty=nameWithType> 类型提供对 <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> 类等效的功能，<xref:System.IO.Ports?displayProperty=nameWithType> 命名空间中的类型可提供对 <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> 类等效的功能。</span><span class="sxs-lookup"><span data-stu-id="a0066-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="a0066-112">类别</span><span class="sxs-lookup"><span data-stu-id="a0066-112">Category</span></span>

<span data-ttu-id="a0066-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0066-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a0066-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a0066-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

