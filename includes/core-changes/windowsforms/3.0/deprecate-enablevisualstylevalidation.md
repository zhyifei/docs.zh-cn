---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936988"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="c5754-101">不支持 EnableVisualStyleValidation 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="c5754-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="c5754-102">.NET Core 3.0 上的 Windows 窗体不支持 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 兼容性开关。</span><span class="sxs-lookup"><span data-stu-id="c5754-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c5754-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="c5754-103">Change description</span></span>

<span data-ttu-id="c5754-104">在 .NET Framework 中，`Switch.System.Windows.Forms.EnableVisualStyleValidation` 兼容性开关使得应用程序可选择不验证以数值格式提供的视觉样式。</span><span class="sxs-lookup"><span data-stu-id="c5754-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="c5754-105">.NET Core 中尚不支持 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 开关。</span><span class="sxs-lookup"><span data-stu-id="c5754-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c5754-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="c5754-106">Version introduced</span></span>

<span data-ttu-id="c5754-107">3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="c5754-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c5754-108">建议操作</span><span class="sxs-lookup"><span data-stu-id="c5754-108">Recommended action</span></span>

<span data-ttu-id="c5754-109">删除此开关。</span><span class="sxs-lookup"><span data-stu-id="c5754-109">Remove the switch.</span></span> <span data-ttu-id="c5754-110">此开关不受支持，且未提供替代功能。</span><span class="sxs-lookup"><span data-stu-id="c5754-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="c5754-111">类别</span><span class="sxs-lookup"><span data-stu-id="c5754-111">Category</span></span>

<span data-ttu-id="c5754-112">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="c5754-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c5754-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="c5754-113">Affected APIs</span></span>

- <span data-ttu-id="c5754-114">无</span><span class="sxs-lookup"><span data-stu-id="c5754-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
