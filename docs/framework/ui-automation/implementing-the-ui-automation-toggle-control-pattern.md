---
title: 实现 UI 自动化 Toggle 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: 75659182fae64c548fe67090b13d43a212e6abae
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679025"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a><span data-ttu-id="98f7b-102">实现 UI 自动化 Toggle 控件模式</span><span class="sxs-lookup"><span data-stu-id="98f7b-102">Implementing the UI Automation Toggle Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="98f7b-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="98f7b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="98f7b-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="98f7b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="98f7b-105">本主题介绍实现 <xref:System.Windows.Automation.Provider.IToggleProvider>的准则和约定，包括有关方法和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="98f7b-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>, including information about methods and properties.</span></span> <span data-ttu-id="98f7b-106">本主题的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="98f7b-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="98f7b-107"><xref:System.Windows.Automation.TogglePattern> 控件模式用于支持可在一组状态间进行循环，并在设置后保持其状态的控件。</span><span class="sxs-lookup"><span data-stu-id="98f7b-107">The <xref:System.Windows.Automation.TogglePattern> control pattern is used to support controls that can cycle through a set of states and maintain a state once set.</span></span> <span data-ttu-id="98f7b-108">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="98f7b-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="98f7b-109">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="98f7b-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="98f7b-110">在实现“切换”控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="98f7b-110">When implementing the Toggle control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="98f7b-111">不保持激活时的状态的控件（如按钮、工具栏按钮和超链接）则必须实现 <xref:System.Windows.Automation.Provider.IInvokeProvider> 。</span><span class="sxs-lookup"><span data-stu-id="98f7b-111">Controls that do not maintain state when activated, such as buttons, toolbar buttons, and hyperlinks, must implement <xref:System.Windows.Automation.Provider.IInvokeProvider> instead.</span></span>  
  
-   <span data-ttu-id="98f7b-112">控件必须按以下顺序在其 <xref:System.Windows.Automation.ToggleState> 间进行循环： <xref:System.Windows.Automation.ToggleState.On>、 <xref:System.Windows.Automation.ToggleState.Off> ，以及 <xref:System.Windows.Automation.ToggleState.Indeterminate>（如果支持）。</span><span class="sxs-lookup"><span data-stu-id="98f7b-112">A control must cycle through its <xref:System.Windows.Automation.ToggleState> in the following order: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> and, if supported, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span></span>  
  
-   <span data-ttu-id="98f7b-113"><xref:System.Windows.Automation.TogglePattern> 不提供 SetState(newState) 方法，因为不按相应的 <xref:System.Windows.Automation.ToggleState> 顺序进行循环即直接设置三态复选框存在问题。</span><span class="sxs-lookup"><span data-stu-id="98f7b-113"><xref:System.Windows.Automation.TogglePattern> does not provide a SetState(newState) method due to issues surrounding the direct setting of a tri-state CheckBox without cycling through its appropriate <xref:System.Windows.Automation.ToggleState> sequence.</span></span>  
  
-   <span data-ttu-id="98f7b-114">单选按钮控件不会实现 <xref:System.Windows.Automation.Provider.IToggleProvider>，因为它不能在其有效状态间进行循环。</span><span class="sxs-lookup"><span data-stu-id="98f7b-114">The RadioButton control does not implement <xref:System.Windows.Automation.Provider.IToggleProvider>, as it is not capable of cycling through its valid states.</span></span>  
  
<a name="Required_Members_for_IToggleProvider"></a>   
## <a name="required-members-for-itoggleprovider"></a><span data-ttu-id="98f7b-115">IToggleProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="98f7b-115">Required Members for IToggleProvider</span></span>  
 <span data-ttu-id="98f7b-116">实现 <xref:System.Windows.Automation.Provider.IToggleProvider>需要以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="98f7b-116">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
|<span data-ttu-id="98f7b-117">必需的成员</span><span class="sxs-lookup"><span data-stu-id="98f7b-117">Required member</span></span>|<span data-ttu-id="98f7b-118">成员类型</span><span class="sxs-lookup"><span data-stu-id="98f7b-118">Member type</span></span>|<span data-ttu-id="98f7b-119">说明</span><span class="sxs-lookup"><span data-stu-id="98f7b-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|<span data-ttu-id="98f7b-120">方法</span><span class="sxs-lookup"><span data-stu-id="98f7b-120">Method</span></span>|<span data-ttu-id="98f7b-121">无</span><span class="sxs-lookup"><span data-stu-id="98f7b-121">None</span></span>|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|<span data-ttu-id="98f7b-122">属性</span><span class="sxs-lookup"><span data-stu-id="98f7b-122">Property</span></span>|<span data-ttu-id="98f7b-123">无</span><span class="sxs-lookup"><span data-stu-id="98f7b-123">None</span></span>|  
  
 <span data-ttu-id="98f7b-124">没有与此控件模式关联的事件。</span><span class="sxs-lookup"><span data-stu-id="98f7b-124">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="98f7b-125">Exceptions</span><span class="sxs-lookup"><span data-stu-id="98f7b-125">Exceptions</span></span>  
 <span data-ttu-id="98f7b-126">没有与此控件模式关联的异常。</span><span class="sxs-lookup"><span data-stu-id="98f7b-126">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f7b-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="98f7b-127">See also</span></span>
- [<span data-ttu-id="98f7b-128">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="98f7b-128">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="98f7b-129">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="98f7b-129">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="98f7b-130">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="98f7b-130">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="98f7b-131">使用 UI 自动化获取复选框的切换状态</span><span class="sxs-lookup"><span data-stu-id="98f7b-131">Get the Toggle State of a Check Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [<span data-ttu-id="98f7b-132">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="98f7b-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="98f7b-133">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="98f7b-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
