---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181810"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="3f8dc-101">不支持 Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="3f8dc-101">Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="3f8dc-102">已在 .NET Framework 4.7.1 中引入 `Switch.System.Windows.Forms.UseLegacyImages` 兼容性开关，但它在 .NET Core 3.0 上的 Windows 窗体中尚不受支持。</span><span class="sxs-lookup"><span data-stu-id="3f8dc-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3f8dc-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="3f8dc-103">Change description</span></span>

<span data-ttu-id="3f8dc-104">在 .NET Framework 4.6.2 及更低版本中，<xref:System.Windows.Forms.RichTextBox> 控件会实例化 Win32 RichEdit 控件 v3.0；而对于面向 .NET Framework 4.7.1 的应用程序，<xref:System.Windows.Forms.RichTextBox> 控件会实例化 RichEdit v4.1（位于 msftedit.dll 中）  。</span><span class="sxs-lookup"><span data-stu-id="3f8dc-104">In the .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control would instantiate the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control would instantiate RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="3f8dc-105">已引入 `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` 兼容性开关，使面向 .NET Framework 4.7.1 及更高版本的应用程序可选择不使用新的 RichEdit v4.1 控件而改用旧的 RichEdit v3 控件。</span><span class="sxs-lookup"><span data-stu-id="3f8dc-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt-out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="3f8dc-106">.NET Core 中尚不支持 `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` 开关。</span><span class="sxs-lookup"><span data-stu-id="3f8dc-106">In .NET Core, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="3f8dc-107">仅支持 <xref:System.Windows.Forms.RichTextBox> 控件的新版本。</span><span class="sxs-lookup"><span data-stu-id="3f8dc-107">Only new versions of the  <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3f8dc-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="3f8dc-108">Version introduced</span></span>

<span data-ttu-id="3f8dc-109">3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="3f8dc-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3f8dc-110">建议的操作</span><span class="sxs-lookup"><span data-stu-id="3f8dc-110">Recommended action</span></span>

<span data-ttu-id="3f8dc-111">删除此开关。</span><span class="sxs-lookup"><span data-stu-id="3f8dc-111">Remove the switch.</span></span> <span data-ttu-id="3f8dc-112">此开关不受支持，且未提供替代功能。</span><span class="sxs-lookup"><span data-stu-id="3f8dc-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="3f8dc-113">类别</span><span class="sxs-lookup"><span data-stu-id="3f8dc-113">Category</span></span>

<span data-ttu-id="3f8dc-114">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="3f8dc-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3f8dc-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="3f8dc-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
