---
ms.openlocfilehash: 07527c247e6ccd53d2a77793946ffc796c3e1cbb
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181773"
---
### <a name="switchsystemwindowsformsuselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="e1569-101">不支持 Switch.System.Windows.Forms.UseLegacyImages 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="e1569-101">Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="e1569-102">已在 .NET Framework 4.8 中引入 `Switch.System.Windows.Forms.UseLegacyImages` 兼容性开关，但它在 .NET Core 3.0 上的 Windows 窗体中尚不受支持。</span><span class="sxs-lookup"><span data-stu-id="e1569-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e1569-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="e1569-103">Change description</span></span>

<span data-ttu-id="e1569-104">自 .NET Framework 4.8 起，`Switch.System.Windows.Forms.UseLegacyImages` 兼容性开关会处理高 DPI 环境中 ClickOnce 方案内可能出现的图像缩放问题。</span><span class="sxs-lookup"><span data-stu-id="e1569-104">Starting with the .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="e1569-105">如果设置为 `true`，则用户可通过此开关在缩放比例设置为大于 100% 的高 DPI 显示器上还原旧的图像缩放行为。</span><span class="sxs-lookup"><span data-stu-id="e1569-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="e1569-106">有关详细信息，请参阅 GitHub 上的 [.NET Framework 4.8 发行说明](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce)。</span><span class="sxs-lookup"><span data-stu-id="e1569-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="e1569-107">.NET Core 中尚不支持 `Switch.System.Windows.Forms.UseLegacyImages` 开关。</span><span class="sxs-lookup"><span data-stu-id="e1569-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e1569-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="e1569-108">Version introduced</span></span>

<span data-ttu-id="e1569-109">3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="e1569-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e1569-110">建议的操作</span><span class="sxs-lookup"><span data-stu-id="e1569-110">Recommended action</span></span>

<span data-ttu-id="e1569-111">删除此开关。</span><span class="sxs-lookup"><span data-stu-id="e1569-111">Remove the switch.</span></span> <span data-ttu-id="e1569-112">此开关不受支持，且未提供替代功能。</span><span class="sxs-lookup"><span data-stu-id="e1569-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="e1569-113">类别</span><span class="sxs-lookup"><span data-stu-id="e1569-113">Category</span></span>

<span data-ttu-id="e1569-114">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="e1569-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e1569-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="e1569-115">Affected APIs</span></span>

- <span data-ttu-id="e1569-116">无</span><span class="sxs-lookup"><span data-stu-id="e1569-116">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
