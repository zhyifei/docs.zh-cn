---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234606"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="93dd8-101">WPF TextBox.Text 可能与数据绑定不同步</span><span class="sxs-lookup"><span data-stu-id="93dd8-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

|   |   |
|---|---|
|<span data-ttu-id="93dd8-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="93dd8-102">Details</span></span>|<span data-ttu-id="93dd8-103">在某些情况下，如果在数据绑定的写入操作期间修改属性，则 <xref:System.Windows.Controls.TextBox.Text> 属性会反映数据绑定属性值的以前的值。</span><span class="sxs-lookup"><span data-stu-id="93dd8-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>|
|<span data-ttu-id="93dd8-104">建议</span><span class="sxs-lookup"><span data-stu-id="93dd8-104">Suggestion</span></span>|<span data-ttu-id="93dd8-105">这不应有负面影响。</span><span class="sxs-lookup"><span data-stu-id="93dd8-105">This should have no negative impact.</span></span> <span data-ttu-id="93dd8-106">不过，你可以通过将 <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> 属性设置为 <code>false</code> 来还原以前的行为。</span><span class="sxs-lookup"><span data-stu-id="93dd8-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to <code>false</code>.</span></span>|
|<span data-ttu-id="93dd8-107">范围</span><span class="sxs-lookup"><span data-stu-id="93dd8-107">Scope</span></span>|<span data-ttu-id="93dd8-108">边缘</span><span class="sxs-lookup"><span data-stu-id="93dd8-108">Edge</span></span>|
|<span data-ttu-id="93dd8-109">版本</span><span class="sxs-lookup"><span data-stu-id="93dd8-109">Version</span></span>|<span data-ttu-id="93dd8-110">4.5</span><span class="sxs-lookup"><span data-stu-id="93dd8-110">4.5</span></span>|
|<span data-ttu-id="93dd8-111">类型</span><span class="sxs-lookup"><span data-stu-id="93dd8-111">Type</span></span>|<span data-ttu-id="93dd8-112">重定目标</span><span class="sxs-lookup"><span data-stu-id="93dd8-112">Retargeting</span></span>|
|<span data-ttu-id="93dd8-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="93dd8-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
