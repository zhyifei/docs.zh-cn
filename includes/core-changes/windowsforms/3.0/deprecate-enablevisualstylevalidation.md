---
ms.openlocfilehash: 97e38685777c7c418c0ccd91f4c433501ecf3aaa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721081"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="f1438-101">不支持 EnableVisualStyleValidation 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="f1438-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="f1438-102">.NET Core 3.0 上的 Windows 窗体不支持 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 兼容性开关。</span><span class="sxs-lookup"><span data-stu-id="f1438-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f1438-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="f1438-103">Change description</span></span>

<span data-ttu-id="f1438-104">在 .NET Framework 中，`Switch.System.Windows.Forms.EnableVisualStyleValidation` 兼容性开关使得应用程序可选择不验证以数值格式提供的视觉样式。</span><span class="sxs-lookup"><span data-stu-id="f1438-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="f1438-105">.NET Core 中尚不支持 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 开关。</span><span class="sxs-lookup"><span data-stu-id="f1438-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f1438-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="f1438-106">Version introduced</span></span>

<span data-ttu-id="f1438-107">3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="f1438-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f1438-108">建议操作</span><span class="sxs-lookup"><span data-stu-id="f1438-108">Recommended action</span></span>

<span data-ttu-id="f1438-109">删除此开关。</span><span class="sxs-lookup"><span data-stu-id="f1438-109">Remove the switch.</span></span> <span data-ttu-id="f1438-110">此开关不受支持，且未提供替代功能。</span><span class="sxs-lookup"><span data-stu-id="f1438-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="f1438-111">类别</span><span class="sxs-lookup"><span data-stu-id="f1438-111">Category</span></span>

<span data-ttu-id="f1438-112">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="f1438-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f1438-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f1438-113">Affected APIs</span></span>

- <span data-ttu-id="f1438-114">无</span><span class="sxs-lookup"><span data-stu-id="f1438-114">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
