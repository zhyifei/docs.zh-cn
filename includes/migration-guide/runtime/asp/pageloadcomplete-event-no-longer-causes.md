---
ms.openlocfilehash: 02a3c1b5a9693535feeab56d9b0f7c9d360749ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235202"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a><span data-ttu-id="ca93d-101">Page.LoadComplete 事件不再导致 System.Web.UI.WebControls.EntityDataSource 控件调用数据绑定</span><span class="sxs-lookup"><span data-stu-id="ca93d-101">Page.LoadComplete event no longer causes System.Web.UI.WebControls.EntityDataSource control to invoke data binding</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ca93d-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="ca93d-102">Details</span></span>|<span data-ttu-id="ca93d-103"><xref:System.Web.UI.Page.LoadComplete> 事件不再导致 <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=name> 控件针对 create/update/delete 参数的更改来调用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="ca93d-103">The <xref:System.Web.UI.Page.LoadComplete> event no longer causes the <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=name> control to invoke data binding for changes to create/update/delete parameters.</span></span> <span data-ttu-id="ca93d-104">此更改消除到数据库的外来行程，防止重置控件的值，并生成与其他数据控件一致的行为，例如 <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=name> 和 <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="ca93d-104">This change eliminates an extraneous trip to the database, prevents the values of controls from being reset, and produces behavior that is consistent with other data controls, such as <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=name> and <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=name>.</span></span> <span data-ttu-id="ca93d-105">在应用程序依赖于在 <xref:System.Web.UI.Page.LoadComplete> 事件中调用数据绑定的极少数情况下，此更改会产生不同的行为。</span><span class="sxs-lookup"><span data-stu-id="ca93d-105">This change produces different behavior in the unlikely event that applications rely on invoking data binding in the <xref:System.Web.UI.Page.LoadComplete> event.</span></span>|
|<span data-ttu-id="ca93d-106">建议</span><span class="sxs-lookup"><span data-stu-id="ca93d-106">Suggestion</span></span>|<span data-ttu-id="ca93d-107">如果需要数据绑定，请在回发之前的事件中手动调用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="ca93d-107">If there is a need for databinding, manually invoke databind in an event that is earlier in the post-back.</span></span>|
|<span data-ttu-id="ca93d-108">范围</span><span class="sxs-lookup"><span data-stu-id="ca93d-108">Scope</span></span>|<span data-ttu-id="ca93d-109">边缘</span><span class="sxs-lookup"><span data-stu-id="ca93d-109">Edge</span></span>|
|<span data-ttu-id="ca93d-110">版本</span><span class="sxs-lookup"><span data-stu-id="ca93d-110">Version</span></span>|<span data-ttu-id="ca93d-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ca93d-111">4.5</span></span>|
|<span data-ttu-id="ca93d-112">类型</span><span class="sxs-lookup"><span data-stu-id="ca93d-112">Type</span></span>|<span data-ttu-id="ca93d-113">运行时</span><span class="sxs-lookup"><span data-stu-id="ca93d-113">Runtime</span></span>|
