---
title: 实现 UI 自动化 Transform 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: d038991da4048e3279ae974cbf4d3e53691349af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645768"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="a3833-102">实现 UI 自动化 Transform 控件模式</span><span class="sxs-lookup"><span data-stu-id="a3833-102">Implementing the UI Automation Transform Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="a3833-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="a3833-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a3833-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="a3833-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a3833-105">本主题介绍实现 <xref:System.Windows.Automation.Provider.ITransformProvider>的准则和约定，包括有关属性、方法和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="a3833-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="a3833-106">本主题的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="a3833-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="a3833-107"><xref:System.Windows.Automation.TransformPattern> 控件模式用于支持可以移动、调整大小或在二维空间中旋转的控件。</span><span class="sxs-lookup"><span data-stu-id="a3833-107">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="a3833-108">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="a3833-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="a3833-109">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="a3833-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="a3833-110">在实现 Transform 控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="a3833-110">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="a3833-111">对此控件模式的支持并不限于桌面上的对象。</span><span class="sxs-lookup"><span data-stu-id="a3833-111">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="a3833-112">如果子级可以移动、调整大小或在容器的边界内自由地旋转，则此控件模式还必须受到容器对象子级的支持。</span><span class="sxs-lookup"><span data-stu-id="a3833-112">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
- <span data-ttu-id="a3833-113">如果移动、旋转对象或调整其大小使得屏幕位置完全处于其容器的坐标之外（例如，当顶层窗口移动到屏幕之外或子对象移动到容器的视区边界之外时），结果导致键盘或鼠标无法访问，则不能如此操作。</span><span class="sxs-lookup"><span data-stu-id="a3833-113">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="a3833-114">在这些情况下，对象被放在尽可能靠近所请求的屏幕坐标位置，而顶部或左侧坐标被覆盖以位于容器边界内。</span><span class="sxs-lookup"><span data-stu-id="a3833-114">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
- <span data-ttu-id="a3833-115">对于多监视器系统，如果一个对象被移动、调整大小或旋转导致完全位于组合桌面屏幕坐标外，则该对象被放置在尽可能靠近所请求坐标的主监视器中。</span><span class="sxs-lookup"><span data-stu-id="a3833-115">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
- <span data-ttu-id="a3833-116">所有参数和属性值都是绝对和独立于区域设置的。</span><span class="sxs-lookup"><span data-stu-id="a3833-116">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="a3833-117">ITransformProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="a3833-117">Required Members for ITransformProvider</span></span>  
 <span data-ttu-id="a3833-118">实现 <xref:System.Windows.Automation.Provider.ITransformProvider>需要以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="a3833-118">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="a3833-119">必需的成员</span><span class="sxs-lookup"><span data-stu-id="a3833-119">Required members</span></span>|<span data-ttu-id="a3833-120">成员类型</span><span class="sxs-lookup"><span data-stu-id="a3833-120">Member type</span></span>|<span data-ttu-id="a3833-121">说明</span><span class="sxs-lookup"><span data-stu-id="a3833-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="a3833-122">属性</span><span class="sxs-lookup"><span data-stu-id="a3833-122">Property</span></span>|<span data-ttu-id="a3833-123">None</span><span class="sxs-lookup"><span data-stu-id="a3833-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="a3833-124">属性</span><span class="sxs-lookup"><span data-stu-id="a3833-124">Property</span></span>|<span data-ttu-id="a3833-125">None</span><span class="sxs-lookup"><span data-stu-id="a3833-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="a3833-126">属性</span><span class="sxs-lookup"><span data-stu-id="a3833-126">Property</span></span>|<span data-ttu-id="a3833-127">None</span><span class="sxs-lookup"><span data-stu-id="a3833-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="a3833-128">方法</span><span class="sxs-lookup"><span data-stu-id="a3833-128">Method</span></span>|<span data-ttu-id="a3833-129">None</span><span class="sxs-lookup"><span data-stu-id="a3833-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="a3833-130">方法</span><span class="sxs-lookup"><span data-stu-id="a3833-130">Method</span></span>|<span data-ttu-id="a3833-131">None</span><span class="sxs-lookup"><span data-stu-id="a3833-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="a3833-132">方法</span><span class="sxs-lookup"><span data-stu-id="a3833-132">Method</span></span>|<span data-ttu-id="a3833-133">None</span><span class="sxs-lookup"><span data-stu-id="a3833-133">None</span></span>|  
  
 <span data-ttu-id="a3833-134">没有与此控件模式关联的事件。</span><span class="sxs-lookup"><span data-stu-id="a3833-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="a3833-135">Exceptions</span><span class="sxs-lookup"><span data-stu-id="a3833-135">Exceptions</span></span>  
 <span data-ttu-id="a3833-136">提供程序必须引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="a3833-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="a3833-137">异常类型</span><span class="sxs-lookup"><span data-stu-id="a3833-137">Exception Type</span></span>|<span data-ttu-id="a3833-138">条件</span><span class="sxs-lookup"><span data-stu-id="a3833-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="a3833-139">-如果<xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty>为 false。</span><span class="sxs-lookup"><span data-stu-id="a3833-139">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="a3833-140">-如果<xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty>为 false。</span><span class="sxs-lookup"><span data-stu-id="a3833-140">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="a3833-141">-如果<xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty>为 false。</span><span class="sxs-lookup"><span data-stu-id="a3833-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3833-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3833-142">See also</span></span>

- [<span data-ttu-id="a3833-143">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="a3833-143">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="a3833-144">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="a3833-144">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="a3833-145">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="a3833-145">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="a3833-146">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="a3833-146">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="a3833-147">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="a3833-147">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
