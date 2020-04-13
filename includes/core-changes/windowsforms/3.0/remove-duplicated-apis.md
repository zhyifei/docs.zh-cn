---
ms.openlocfilehash: 0be59258df10aa13920551f011d68bc8efe20b93
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888099"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="a6b3f-101">从 Windows 窗体中删除了重复的 API</span><span class="sxs-lookup"><span data-stu-id="a6b3f-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="a6b3f-102">从 .NET Core 3.0 预览版 4 开始，在 <xref:System.Windows.Forms?displayProperty=fullName> 命名空间中意外复制的许多 API 已从 .NET Core 3.0 RC1 中删除。</span><span class="sxs-lookup"><span data-stu-id="a6b3f-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a6b3f-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="a6b3f-103">Change description</span></span>

<span data-ttu-id="a6b3f-104">.NET Core 3.0 预览版 4 在无意中复制了 <xref:System.ComponentModel.Design?displayProperty=fullName> 命名空间中已经存在的 <xref:System.Windows.Forms?displayProperty=fullName> 命名空间中的许多类型。</span><span class="sxs-lookup"><span data-stu-id="a6b3f-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="a6b3f-105">从 .NET Core 3.0 RC1 开始，这些重复的类型不再可用。</span><span class="sxs-lookup"><span data-stu-id="a6b3f-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="a6b3f-106">下表列出了原始类型及其重复类型：</span><span class="sxs-lookup"><span data-stu-id="a6b3f-106">The following table shows lists the original type and its duplicated type:</span></span>

> [!div class="mx-tdCol2BreakAll"]
> |<span data-ttu-id="a6b3f-107">原始类型</span><span class="sxs-lookup"><span data-stu-id="a6b3f-107">Original type</span></span>|<span data-ttu-id="a6b3f-108">重复类型</span><span class="sxs-lookup"><span data-stu-id="a6b3f-108">Duplicated type</span></span>|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="a6b3f-109">引入的版本</span><span class="sxs-lookup"><span data-stu-id="a6b3f-109">Version introduced</span></span>

<span data-ttu-id="a6b3f-110">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="a6b3f-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a6b3f-111">建议操作</span><span class="sxs-lookup"><span data-stu-id="a6b3f-111">Recommended action</span></span>

<span data-ttu-id="a6b3f-112">更新代码以引用原始类型，如表的“原始类型”列中所示  。</span><span class="sxs-lookup"><span data-stu-id="a6b3f-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="a6b3f-113">类别</span><span class="sxs-lookup"><span data-stu-id="a6b3f-113">Category</span></span>

<span data-ttu-id="a6b3f-114">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="a6b3f-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a6b3f-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a6b3f-115">Affected APIs</span></span>

- <span data-ttu-id="a6b3f-116">无。</span><span class="sxs-lookup"><span data-stu-id="a6b3f-116">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis.

-->
