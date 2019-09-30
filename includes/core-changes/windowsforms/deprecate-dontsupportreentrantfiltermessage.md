---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181846"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="4a2e2-101">不支持 Switch.System.Windows.Forms.DontSupportReentrantFilterMessage 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="4a2e2-101">Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="4a2e2-102">已在 .NET Framework 4.6.1 中引入 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 兼容性开关，但它在 .NET Core 3.0 上的 Windows 窗体中尚不受支持。</span><span class="sxs-lookup"><span data-stu-id="4a2e2-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4a2e2-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="4a2e2-103">Change description</span></span>

<span data-ttu-id="4a2e2-104">自 .NET Framework 4.6.1 起，`Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 兼容性开关可处理通过自定义 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 实现调用 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 消息时可能引发的 <xref:System.IndexOutOfRangeException> 异常。</span><span class="sxs-lookup"><span data-stu-id="4a2e2-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="4a2e2-105">有关详细信息，请参阅[缓解：自定义 IMessageFilter.PreFilterMessage 实现](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)。</span><span class="sxs-lookup"><span data-stu-id="4a2e2-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="4a2e2-106">.NET Core 中尚不支持 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 开关。</span><span class="sxs-lookup"><span data-stu-id="4a2e2-106">In .NET Core, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4a2e2-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="4a2e2-107">Version introduced</span></span>

<span data-ttu-id="4a2e2-108">3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="4a2e2-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4a2e2-109">建议的操作</span><span class="sxs-lookup"><span data-stu-id="4a2e2-109">Recommended action</span></span>

<span data-ttu-id="4a2e2-110">删除此开关。</span><span class="sxs-lookup"><span data-stu-id="4a2e2-110">Remove the switch.</span></span> <span data-ttu-id="4a2e2-111">此开关不受支持，且未提供替代功能。</span><span class="sxs-lookup"><span data-stu-id="4a2e2-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="4a2e2-112">类别</span><span class="sxs-lookup"><span data-stu-id="4a2e2-112">Category</span></span>

<span data-ttu-id="4a2e2-113">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="4a2e2-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4a2e2-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="4a2e2-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
