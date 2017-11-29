---
title: "实现 UI 自动化 Value 控件模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
caps.latest.revision: "25"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 23e71c4ce230221f82172a0e5429fc362379869c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-value-control-pattern"></a><span data-ttu-id="723cf-102">实现 UI 自动化 Value 控件模式</span><span class="sxs-lookup"><span data-stu-id="723cf-102">Implementing the UI Automation Value Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="723cf-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="723cf-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="723cf-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="723cf-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="723cf-105">本主题介绍了实现 <xref:System.Windows.Automation.Provider.IValueProvider>的准则和约定，包括有关事件和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="723cf-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IValueProvider>, including information on events and properties.</span></span> <span data-ttu-id="723cf-106">本主题的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="723cf-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="723cf-107"><xref:System.Windows.Automation.ValuePattern> 控件模式用于支持具有未跨越范围的内部值的控件，以及可用字符串表示的控件。</span><span class="sxs-lookup"><span data-stu-id="723cf-107">The <xref:System.Windows.Automation.ValuePattern> control pattern is used to support controls that have an intrinsic value not spanning a range and that can be represented as a string.</span></span> <span data-ttu-id="723cf-108">此字符串是可编辑的，具体取决于控件及其设置。</span><span class="sxs-lookup"><span data-stu-id="723cf-108">This string can be editable, depending on the control and its settings.</span></span> <span data-ttu-id="723cf-109">有关实现此模式的控件的示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="723cf-109">For examples of controls that implement this pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="723cf-110">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="723cf-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="723cf-111">在实现 Value 控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="723cf-111">When implementing the Value control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="723cf-112">如果任何项的值是可编辑的，则诸如 <xref:System.Windows.Automation.ControlType.ListItem> 和 <xref:System.Windows.Automation.ControlType.TreeItem> 等控件必须支持 <xref:System.Windows.Automation.ValuePattern> ，而无论控件的当前编辑模式。</span><span class="sxs-lookup"><span data-stu-id="723cf-112">Controls such as <xref:System.Windows.Automation.ControlType.ListItem> and <xref:System.Windows.Automation.ControlType.TreeItem> must support <xref:System.Windows.Automation.ValuePattern> if the value of any of the items is editable, regardless of the current edit mode of the control.</span></span> <span data-ttu-id="723cf-113">如果子项是可编辑的，则父控件还必须支持 <xref:System.Windows.Automation.ValuePattern> 。</span><span class="sxs-lookup"><span data-stu-id="723cf-113">The parent control must also support <xref:System.Windows.Automation.ValuePattern> if the child items are editable.</span></span>  
  
 <span data-ttu-id="723cf-114">![可编辑列表项。] (../../../docs/framework/ui-automation/media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")</span><span class="sxs-lookup"><span data-stu-id="723cf-114">![Editable list item.](../../../docs/framework/ui-automation/media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")</span></span>  
<span data-ttu-id="723cf-115">可编辑列表项的示例</span><span class="sxs-lookup"><span data-stu-id="723cf-115">Example of an Editable List Item</span></span>  
  
-   <span data-ttu-id="723cf-116">单行编辑控件支持通过实现 <xref:System.Windows.Automation.Provider.IValueProvider>编程访问其内容。</span><span class="sxs-lookup"><span data-stu-id="723cf-116">Single-line edit controls support programmatic access to their contents by implementing <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span> <span data-ttu-id="723cf-117">但是，多行编辑控件不实现 <xref:System.Windows.Automation.Provider.IValueProvider>；相反，它们通过实现 <xref:System.Windows.Automation.Provider.ITextProvider>来提供对其内容的访问。</span><span class="sxs-lookup"><span data-stu-id="723cf-117">However, multi-line edit controls do not implement <xref:System.Windows.Automation.Provider.IValueProvider>; instead they provide access to their content by implementing <xref:System.Windows.Automation.Provider.ITextProvider>.</span></span>  
  
-   <span data-ttu-id="723cf-118">若要检索多行编辑控件的文本内容，控件必须实现 <xref:System.Windows.Automation.Provider.ITextProvider>。</span><span class="sxs-lookup"><span data-stu-id="723cf-118">To retrieve the textual contents of a multi-line edit control, the control must implement <xref:System.Windows.Automation.Provider.ITextProvider>.</span></span> <span data-ttu-id="723cf-119">但是， <xref:System.Windows.Automation.Provider.ITextProvider> 不支持设置控件的值。</span><span class="sxs-lookup"><span data-stu-id="723cf-119">However, <xref:System.Windows.Automation.Provider.ITextProvider> does not support setting the value of a control.</span></span>  
  
-   <span data-ttu-id="723cf-120"><xref:System.Windows.Automation.Provider.IValueProvider> 不支持检索格式设置信息或子字符串值。</span><span class="sxs-lookup"><span data-stu-id="723cf-120"><xref:System.Windows.Automation.Provider.IValueProvider> does not support the retrieval of formatting information or substring values.</span></span> <span data-ttu-id="723cf-121">在这些情况下，请实现 <xref:System.Windows.Automation.Provider.ITextProvider> 。</span><span class="sxs-lookup"><span data-stu-id="723cf-121">Implement <xref:System.Windows.Automation.Provider.ITextProvider> in these scenarios.</span></span>  
  
-   <span data-ttu-id="723cf-122"><xref:System.Windows.Automation.Provider.IValueProvider> 必须由诸如 **中的“颜色选取器”**[!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] 选择控件（如下所示）之类的控件实现，该控件支持颜色值（例如，“黄色”）与等效的内部 [!INCLUDE[TLA#tla_rgb](../../../includes/tlasharptla-rgb-md.md)] 结构之间的字符串映射。</span><span class="sxs-lookup"><span data-stu-id="723cf-122"><xref:System.Windows.Automation.Provider.IValueProvider> must be implemented by controls such as the **Color Picker** selection control from [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (illustrated below), which supports string mapping between a color value (for example, "yellow") and an equivalent internal [!INCLUDE[TLA#tla_rgb](../../../includes/tlasharptla-rgb-md.md)] structure.</span></span>  
  
 <span data-ttu-id="723cf-123">![突出显示黄色的颜色选取器。] (../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span><span class="sxs-lookup"><span data-stu-id="723cf-123">![Color picker with yellow highlighted.](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span></span>  
<span data-ttu-id="723cf-124">颜色样本字符串映射的示例</span><span class="sxs-lookup"><span data-stu-id="723cf-124">Example of Color Swatch String Mapping</span></span>  
  
-   <span data-ttu-id="723cf-125">在允许调用 <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> 之前，控件应将其 `true` 设置为 <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> ，并将其 `false` 设置为 <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>。</span><span class="sxs-lookup"><span data-stu-id="723cf-125">A control should have its <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> set to `true` and its <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> set to `false` before allowing a call to <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-ivalueprovider"></a><span data-ttu-id="723cf-126">IValueProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="723cf-126">Required Members for IValueProvider</span></span>  
 <span data-ttu-id="723cf-127">实现 <xref:System.Windows.Automation.Provider.IValueProvider>需要以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="723cf-127">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span>  
  
|<span data-ttu-id="723cf-128">必需的成员</span><span class="sxs-lookup"><span data-stu-id="723cf-128">Required members</span></span>|<span data-ttu-id="723cf-129">成员类型</span><span class="sxs-lookup"><span data-stu-id="723cf-129">Member type</span></span>|<span data-ttu-id="723cf-130">备注</span><span class="sxs-lookup"><span data-stu-id="723cf-130">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|<span data-ttu-id="723cf-131">属性</span><span class="sxs-lookup"><span data-stu-id="723cf-131">Property</span></span>|<span data-ttu-id="723cf-132">无</span><span class="sxs-lookup"><span data-stu-id="723cf-132">None</span></span>|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|<span data-ttu-id="723cf-133">属性</span><span class="sxs-lookup"><span data-stu-id="723cf-133">Property</span></span>|<span data-ttu-id="723cf-134">无</span><span class="sxs-lookup"><span data-stu-id="723cf-134">None</span></span>|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|<span data-ttu-id="723cf-135">方法</span><span class="sxs-lookup"><span data-stu-id="723cf-135">Method</span></span>|<span data-ttu-id="723cf-136">无</span><span class="sxs-lookup"><span data-stu-id="723cf-136">None</span></span>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="723cf-137">异常</span><span class="sxs-lookup"><span data-stu-id="723cf-137">Exceptions</span></span>  
 <span data-ttu-id="723cf-138">提供程序必须引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="723cf-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="723cf-139">异常类型</span><span class="sxs-lookup"><span data-stu-id="723cf-139">Exception type</span></span>|<span data-ttu-id="723cf-140">条件</span><span class="sxs-lookup"><span data-stu-id="723cf-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="723cf-141">-如果区域设置特定的信息传递给如格式不正确的日期格式不正确的控件。</span><span class="sxs-lookup"><span data-stu-id="723cf-141">-   If locale-specific information is passed to a control in an incorrect format such as an incorrectly formatted date.</span></span>|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="723cf-142">-如果无法将新值从字符串转换为格式控件可识别。</span><span class="sxs-lookup"><span data-stu-id="723cf-142">-   If a new value cannot be converted from a string to a format the control recognizes.</span></span>|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="723cf-143">-当尝试操作未启用的控件。</span><span class="sxs-lookup"><span data-stu-id="723cf-143">-   When an attempt is made to manipulate a control that is not enabled.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="723cf-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="723cf-144">See Also</span></span>  
 [<span data-ttu-id="723cf-145">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="723cf-145">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="723cf-146">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="723cf-146">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="723cf-147">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="723cf-147">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="723cf-148">TextPattern 插入文本示例</span><span class="sxs-lookup"><span data-stu-id="723cf-148">TextPattern Insert Text Sample</span></span>](http://msdn.microsoft.com/en-us/67353f93-7ee2-42f2-ab76-5c078cf6ca16)  
 [<span data-ttu-id="723cf-149">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="723cf-149">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="723cf-150">使用在 UI 自动化中缓存</span><span class="sxs-lookup"><span data-stu-id="723cf-150">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
