---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937008"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="549c1-101">不支持 AllowUpdateChildControlIndexForTabControls 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="549c1-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="549c1-102">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 兼容性开关在 .NET Framework 4.6 及更高版本上的 Windows 窗体中受支持，但在自 .NET Core 3.0 起的 Windows 窗体中不受支持。</span><span class="sxs-lookup"><span data-stu-id="549c1-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="549c1-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="549c1-103">Change description</span></span>

<span data-ttu-id="549c1-104">在 .NET Framework 4.6 及更高版本中，选中选项卡会对其控件集合重新排序。</span><span class="sxs-lookup"><span data-stu-id="549c1-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="549c1-105">借助 `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 兼容性开关，应用程序可在不需要此类重新排序时跳过此行为。</span><span class="sxs-lookup"><span data-stu-id="549c1-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="549c1-106">.NET Core 中尚不支持 `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` 开关。</span><span class="sxs-lookup"><span data-stu-id="549c1-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="549c1-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="549c1-107">Version introduced</span></span>

<span data-ttu-id="549c1-108">3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="549c1-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="549c1-109">建议操作</span><span class="sxs-lookup"><span data-stu-id="549c1-109">Recommended action</span></span>

<span data-ttu-id="549c1-110">删除此开关。</span><span class="sxs-lookup"><span data-stu-id="549c1-110">Remove the switch.</span></span> <span data-ttu-id="549c1-111">此开关不受支持，且未提供替代功能。</span><span class="sxs-lookup"><span data-stu-id="549c1-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="549c1-112">类别</span><span class="sxs-lookup"><span data-stu-id="549c1-112">Category</span></span>

<span data-ttu-id="549c1-113">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="549c1-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="549c1-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="549c1-114">Affected APIs</span></span>

- <span data-ttu-id="549c1-115">None</span><span class="sxs-lookup"><span data-stu-id="549c1-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
