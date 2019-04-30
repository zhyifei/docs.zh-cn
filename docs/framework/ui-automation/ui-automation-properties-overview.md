---
title: UI 自动化属性概述
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 9028f9f99ee22dd480d817bc8aa94c7113a15c9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032300"
---
# <a name="ui-automation-properties-overview"></a><span data-ttu-id="3851e-102">UI 自动化属性概述</span><span class="sxs-lookup"><span data-stu-id="3851e-102">UI Automation Properties Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="3851e-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="3851e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3851e-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="3851e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3851e-105">UI 自动化提供程序公开 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 元素的属性。</span><span class="sxs-lookup"><span data-stu-id="3851e-105">UI Automation providers expose properties on [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements.</span></span> <span data-ttu-id="3851e-106">这些属性使 UI 自动化客户端应用程序能够发现 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]各部分（特别是控件）的信息，包括静态数据和动态数据。</span><span class="sxs-lookup"><span data-stu-id="3851e-106">These properties enable UI Automation client applications to discover information about pieces of the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especially controls, including both static and dynamic data.</span></span>  
  
 <span data-ttu-id="3851e-107">本节概括了 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 属性。</span><span class="sxs-lookup"><span data-stu-id="3851e-107">This section gives a broad overview of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] properties.</span></span> <span data-ttu-id="3851e-108">下面各主题中提供了更具体的信息：</span><span class="sxs-lookup"><span data-stu-id="3851e-108">More specific information is given in the following topics:</span></span>  
  
- [<span data-ttu-id="3851e-109">客户端的 UI 自动化属性</span><span class="sxs-lookup"><span data-stu-id="3851e-109">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
  
- [<span data-ttu-id="3851e-110">服务器端 UI 自动化提供程序实现</span><span class="sxs-lookup"><span data-stu-id="3851e-110">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>   
## <a name="property-identifiers"></a><span data-ttu-id="3851e-111">属性标识符</span><span class="sxs-lookup"><span data-stu-id="3851e-111">Property Identifiers</span></span>  
 <span data-ttu-id="3851e-112">每个属性都由一个数字和名称标识。</span><span class="sxs-lookup"><span data-stu-id="3851e-112">Every property is identified by a number and a name.</span></span> <span data-ttu-id="3851e-113">属性的名称仅用于调试和诊断。</span><span class="sxs-lookup"><span data-stu-id="3851e-113">The names of properties are used only for debugging and diagnosis.</span></span> <span data-ttu-id="3851e-114">提供程序使用数字 [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] 来标识传入的属性请求。</span><span class="sxs-lookup"><span data-stu-id="3851e-114">Providers use the numeric [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] to identify incoming property requests.</span></span> <span data-ttu-id="3851e-115">但是，客户端应用程序只使用封装了数字和名称的 <xref:System.Windows.Automation.AutomationProperty>来标识它们希望检索的属性。</span><span class="sxs-lookup"><span data-stu-id="3851e-115">Client applications, however, only use <xref:System.Windows.Automation.AutomationProperty>, which encapsulates the number and name, to identify properties they wish to retrieve.</span></span>  
  
 <span data-ttu-id="3851e-116">表示特定属性的<xref:System.Windows.Automation.AutomationProperty> 对象在各个类中以字段的形式提供。</span><span class="sxs-lookup"><span data-stu-id="3851e-116"><xref:System.Windows.Automation.AutomationProperty> objects representing particular properties are available as fields in various classes.</span></span> <span data-ttu-id="3851e-117">出于安全原因，UI 自动化提供程序将从 Uiautomationtypes.dll 中包含的一组单独的类中获取这些对象。</span><span class="sxs-lookup"><span data-stu-id="3851e-117">For security reasons, UI Automation providers obtain these objects from a separate set of classes that are contained in Uiautomationtypes.dll.</span></span>  
  
 <span data-ttu-id="3851e-118">下表按包含 <xref:System.Windows.Automation.AutomationProperty>[!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3851e-118">The following table categorizes properties by the classes that contain the <xref:System.Windows.Automation.AutomationProperty>[!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)].</span></span>  
  
|<span data-ttu-id="3851e-119">属性的种类</span><span class="sxs-lookup"><span data-stu-id="3851e-119">Kinds of properties</span></span>|<span data-ttu-id="3851e-120">客户端从中获取 ID</span><span class="sxs-lookup"><span data-stu-id="3851e-120">Clients get IDs from</span></span>|<span data-ttu-id="3851e-121">提供程序从中获取 ID</span><span class="sxs-lookup"><span data-stu-id="3851e-121">Providers get IDs from</span></span>|  
|-------------------------|--------------------------|----------------------------|  
|<span data-ttu-id="3851e-122">所有元素共有的属性（请参阅下表）</span><span class="sxs-lookup"><span data-stu-id="3851e-122">Properties common to all elements (see following tables)</span></span>|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|<span data-ttu-id="3851e-123">停靠窗口的位置</span><span class="sxs-lookup"><span data-stu-id="3851e-123">Position of a docking window</span></span>|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|<span data-ttu-id="3851e-124">可展开和折叠的元素的状态</span><span class="sxs-lookup"><span data-stu-id="3851e-124">State of an element that can expand and collapse</span></span>|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|<span data-ttu-id="3851e-125">网格中某项的属性</span><span class="sxs-lookup"><span data-stu-id="3851e-125">Properties of an item in a grid</span></span>|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|<span data-ttu-id="3851e-126">网格的属性</span><span class="sxs-lookup"><span data-stu-id="3851e-126">Properties of a grid</span></span>|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|<span data-ttu-id="3851e-127">具有多个视图的元素的当前和支持的视图</span><span class="sxs-lookup"><span data-stu-id="3851e-127">Current and supported view of an element that has multiple views</span></span>|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|<span data-ttu-id="3851e-128">在一定范围的值内移动的元素（如滑块）的属性</span><span class="sxs-lookup"><span data-stu-id="3851e-128">Properties of an element that moves over a range of values, such as a slider</span></span>|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|<span data-ttu-id="3851e-129">滚动窗口的属性</span><span class="sxs-lookup"><span data-stu-id="3851e-129">Properties of a scrolling window</span></span>|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|<span data-ttu-id="3851e-130">可选择的某项（如列表中的某项）的状态和容器</span><span class="sxs-lookup"><span data-stu-id="3851e-130">Status and container of an item that can be selected, as in a list</span></span>|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|<span data-ttu-id="3851e-131">包含选择项的控件的属性</span><span class="sxs-lookup"><span data-stu-id="3851e-131">Properties of a control that contains selection items</span></span>|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|<span data-ttu-id="3851e-132">表中某项的列和行标题</span><span class="sxs-lookup"><span data-stu-id="3851e-132">Column and row headers of an item in a table</span></span>|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|<span data-ttu-id="3851e-133">表的列和行标题以及方向</span><span class="sxs-lookup"><span data-stu-id="3851e-133">Column and row headers, and orientation, of a table</span></span>|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|<span data-ttu-id="3851e-134">切换控件的状态</span><span class="sxs-lookup"><span data-stu-id="3851e-134">State of a toggle control</span></span>|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|<span data-ttu-id="3851e-135">可移动、旋转、或调整大小的元素的功能</span><span class="sxs-lookup"><span data-stu-id="3851e-135">Capabilities of an element that can be moved, rotated, or resized</span></span>|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|<span data-ttu-id="3851e-136">具有值的元素的值和读/写功能</span><span class="sxs-lookup"><span data-stu-id="3851e-136">Value and read/write capabilities of an element that has a value</span></span>|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|<span data-ttu-id="3851e-137">窗口的功能和状态</span><span class="sxs-lookup"><span data-stu-id="3851e-137">Capabilities and state of a window</span></span>|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>   
## <a name="properties-by-category"></a><span data-ttu-id="3851e-138">按类别列出的属性</span><span class="sxs-lookup"><span data-stu-id="3851e-138">Properties by Category</span></span>  
 <span data-ttu-id="3851e-139">下表对其 [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] 位于 <xref:System.Windows.Automation.AutomationElement> 和 <xref:System.Windows.Automation.AutomationElementIdentifiers>中的属性进行分类。</span><span class="sxs-lookup"><span data-stu-id="3851e-139">The following tables categorize the properties whose [!INCLUDE[TLA2#tla_id#plural](../../../includes/tla2sharptla-idsharpplural-md.md)] are found in <xref:System.Windows.Automation.AutomationElement> and <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span></span> <span data-ttu-id="3851e-140">这些属性是所有控件共有的。</span><span class="sxs-lookup"><span data-stu-id="3851e-140">These properties are common to all controls.</span></span> <span data-ttu-id="3851e-141">很少一些属性在提供程序应用程序的生存期内可能是静态的；大多数动态属性都与控件模式关联。</span><span class="sxs-lookup"><span data-stu-id="3851e-141">All but a few of them are likely to be static over the lifetime of the provider application; most dynamic properties are associated with control patterns.</span></span>  
  
 <span data-ttu-id="3851e-142">除 **和** 之外， <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A><xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>“属性访问”列还列出了每个属性的任何其他访问器。</span><span class="sxs-lookup"><span data-stu-id="3851e-142">The **Property Access** column lists any other accessors for each property, in addition to <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> and <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span></span> <span data-ttu-id="3851e-143">有关在客户端应用程序中获取属性的详细信息，请参阅 [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="3851e-143">For more information on getting properties in a client application, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3851e-144">有关每个属性的具体信息，请访问  “属性访问”列中的链接。</span><span class="sxs-lookup"><span data-stu-id="3851e-144">For specific information about each property, follow the link in the **Property Access** column.</span></span>  
  
### <a name="display-characteristics"></a><span data-ttu-id="3851e-145">显示特征</span><span class="sxs-lookup"><span data-stu-id="3851e-145">Display Characteristics</span></span>  
  
|<span data-ttu-id="3851e-146">属性标识符</span><span class="sxs-lookup"><span data-stu-id="3851e-146">Property identifier</span></span>|<span data-ttu-id="3851e-147">和</span><span class="sxs-lookup"><span data-stu-id="3851e-147">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|<span data-ttu-id="3851e-148">n/a</span><span class="sxs-lookup"><span data-stu-id="3851e-148">n/a</span></span>|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a><span data-ttu-id="3851e-149">元素类型</span><span class="sxs-lookup"><span data-stu-id="3851e-149">Element Type</span></span>  
  
|<span data-ttu-id="3851e-150">属性标识符</span><span class="sxs-lookup"><span data-stu-id="3851e-150">Property identifier</span></span>|<span data-ttu-id="3851e-151">和</span><span class="sxs-lookup"><span data-stu-id="3851e-151">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a><span data-ttu-id="3851e-152">标识</span><span class="sxs-lookup"><span data-stu-id="3851e-152">Identification</span></span>  
  
|<span data-ttu-id="3851e-153">属性标识符</span><span class="sxs-lookup"><span data-stu-id="3851e-153">Property identifier</span></span>|<span data-ttu-id="3851e-154">和</span><span class="sxs-lookup"><span data-stu-id="3851e-154">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a><span data-ttu-id="3851e-155">交互</span><span class="sxs-lookup"><span data-stu-id="3851e-155">Interaction</span></span>  
  
|<span data-ttu-id="3851e-156">属性标识符</span><span class="sxs-lookup"><span data-stu-id="3851e-156">Property identifier</span></span>|<span data-ttu-id="3851e-157">和</span><span class="sxs-lookup"><span data-stu-id="3851e-157">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a><span data-ttu-id="3851e-158">对模式的支持</span><span class="sxs-lookup"><span data-stu-id="3851e-158">Support for Patterns</span></span>  
  
|<span data-ttu-id="3851e-159">属性标识符</span><span class="sxs-lookup"><span data-stu-id="3851e-159">Property identifier</span></span>|<span data-ttu-id="3851e-160">和</span><span class="sxs-lookup"><span data-stu-id="3851e-160">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a><span data-ttu-id="3851e-161">杂项</span><span class="sxs-lookup"><span data-stu-id="3851e-161">Miscellaneous</span></span>  
  
|<span data-ttu-id="3851e-162">属性标识符</span><span class="sxs-lookup"><span data-stu-id="3851e-162">Property identifier</span></span>|<span data-ttu-id="3851e-163">和</span><span class="sxs-lookup"><span data-stu-id="3851e-163">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>   
## <a name="localization"></a><span data-ttu-id="3851e-164">本地化</span><span class="sxs-lookup"><span data-stu-id="3851e-164">Localization</span></span>  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="3851e-165">提供程序应按照操作系统的语言呈现下列属性：</span><span class="sxs-lookup"><span data-stu-id="3851e-165">providers should present the following properties in the language of the operating system:</span></span>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>   
## <a name="properties-and-events"></a><span data-ttu-id="3851e-166">属性和事件</span><span class="sxs-lookup"><span data-stu-id="3851e-166">Properties and Events</span></span>  
 <span data-ttu-id="3851e-167">属性更改事件的概念与 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 中的属性密切相关。</span><span class="sxs-lookup"><span data-stu-id="3851e-167">Closely tied in with the properties in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is the concept of property-changed events.</span></span> <span data-ttu-id="3851e-168">对于动态属性，客户端应用程序需要一种途径来了解属性值已更改，以便它能够用某种其他方式更新信息缓存或对新信息做出响应。</span><span class="sxs-lookup"><span data-stu-id="3851e-168">For dynamic properties, the client application needs a way to know that a property value has changed, so that it can update its cache of information or react to the new information in some other way.</span></span>  
  
 <span data-ttu-id="3851e-169">当 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 中的内容发生更改时，提供程序将引发事件。</span><span class="sxs-lookup"><span data-stu-id="3851e-169">Providers raise events when something in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] changes.</span></span> <span data-ttu-id="3851e-170">例如，如果选中或清除了复选框，则提供程序的切换模式实现将引发属性更改事件。</span><span class="sxs-lookup"><span data-stu-id="3851e-170">For example, if a check box is selected or cleared, a property-changed event is raised by the provider's implementation of the Toggle pattern.</span></span> <span data-ttu-id="3851e-171">提供程序可以有选择地引发事件，具体取决于任何客户端是在侦听事件还是在侦听特定事件。</span><span class="sxs-lookup"><span data-stu-id="3851e-171">Providers can raise events selectively, depending on whether any clients are listening for events, or listening for specific events.</span></span>  
  
 <span data-ttu-id="3851e-172">并非所有属性更改都会引发事件；这完全由元素的 UI 自动化提供程序实现所决定。</span><span class="sxs-lookup"><span data-stu-id="3851e-172">Not all property changes raise events; that is entirely up to the implementation of the UI Automation provider for the element.</span></span> <span data-ttu-id="3851e-173">例如，列表框的标准代理提供程序在 <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> 更改时不会引发事件。</span><span class="sxs-lookup"><span data-stu-id="3851e-173">For example, the standard proxy providers for list boxes do not raise an event when the <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> changes.</span></span> <span data-ttu-id="3851e-174">相反，在这种情况下，应用程序必须侦听 <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>。</span><span class="sxs-lookup"><span data-stu-id="3851e-174">In this case, the application instead must listen for an <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span></span>  
  
 <span data-ttu-id="3851e-175">客户端通过订阅事件来侦听事件。</span><span class="sxs-lookup"><span data-stu-id="3851e-175">Clients listen for events by subscribing to them.</span></span> <span data-ttu-id="3851e-176">订阅事件是指创建可处理事件的委托方法，然后将方法随将在这些方法中处理的特定事件一起传递给 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="3851e-176">Subscribing to events means creating delegate methods that can handle the events, and then passing the methods to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] along with the specific events that will be dealt with in those methods.</span></span> <span data-ttu-id="3851e-177">特别是对于属性更改事件，客户端必须实现 <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="3851e-177">For property-changed events in particular, clients must implement <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3851e-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="3851e-178">See also</span></span>

- [<span data-ttu-id="3851e-179">在 UI 自动化客户端中缓存</span><span class="sxs-lookup"><span data-stu-id="3851e-179">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
- [<span data-ttu-id="3851e-180">客户端的 UI 自动化属性</span><span class="sxs-lookup"><span data-stu-id="3851e-180">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="3851e-181">服务器端 UI 自动化提供程序实现</span><span class="sxs-lookup"><span data-stu-id="3851e-181">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
- [<span data-ttu-id="3851e-182">基于属性条件查找 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="3851e-182">Find a UI Automation Element Based on a Property Condition</span></span>](../../../docs/framework/ui-automation/find-a-ui-automation-element-based-on-a-property-condition.md)
- [<span data-ttu-id="3851e-183">从 UI 自动化提供程序返回属性</span><span class="sxs-lookup"><span data-stu-id="3851e-183">Return Properties from a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/return-properties-from-a-ui-automation-provider.md)
- [<span data-ttu-id="3851e-184">从 UI 自动化提供程序引发事件</span><span class="sxs-lookup"><span data-stu-id="3851e-184">Raise Events from a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/raise-events-from-a-ui-automation-provider.md)
