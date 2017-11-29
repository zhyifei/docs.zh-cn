---
title: "Windows 窗体数据绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60a9f66fec64ceda71dd5b70211b897c84113429
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="windows-forms-data-binding"></a><span data-ttu-id="2792f-102">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="2792f-102">Windows Forms Data Binding</span></span>
<span data-ttu-id="2792f-103">Windows 窗体中的数据绑定使你可以显示和更改窗体上的控件中的数据源的信息。</span><span class="sxs-lookup"><span data-stu-id="2792f-103">Data binding in Windows Forms gives you the means to display and make changes to information from a data source in controls on the form.</span></span> <span data-ttu-id="2792f-104">可以绑定到传统数据源和几乎任何包含数据的结构。</span><span class="sxs-lookup"><span data-stu-id="2792f-104">You can bind to both traditional data sources as well as almost any structure that contains data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2792f-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="2792f-105">In This Section</span></span>  
 [<span data-ttu-id="2792f-106">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="2792f-106">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 <span data-ttu-id="2792f-107">提供了 Windows 窗体中的数据绑定概述。</span><span class="sxs-lookup"><span data-stu-id="2792f-107">Provides an overview of data binding in Windows Forms.</span></span>  
  
 [<span data-ttu-id="2792f-108">Windows 窗体支持的数据源</span><span class="sxs-lookup"><span data-stu-id="2792f-108">Data Sources Supported by Windows Forms</span></span>](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 <span data-ttu-id="2792f-109">介绍了可以与 Windows 窗体一起使用的数据源。</span><span class="sxs-lookup"><span data-stu-id="2792f-109">Describes the data sources that can be used with Windows Forms.</span></span>  
  
 [<span data-ttu-id="2792f-110">与数据绑定相关的接口</span><span class="sxs-lookup"><span data-stu-id="2792f-110">Interfaces Related to Data Binding</span></span>](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 <span data-ttu-id="2792f-111">介绍了几种与 Windows 窗体数据绑定一起使用的接口。</span><span class="sxs-lookup"><span data-stu-id="2792f-111">Describes several of the interfaces used with Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="2792f-112">如何：在 Windows 窗体中浏览数据</span><span class="sxs-lookup"><span data-stu-id="2792f-112">How to: Navigate Data in Windows Forms</span></span>](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 <span data-ttu-id="2792f-113">演示如何在数据源中的项之间进行导航。</span><span class="sxs-lookup"><span data-stu-id="2792f-113">Shows how to navigate through items in a data source.</span></span>  
  
 [<span data-ttu-id="2792f-114">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="2792f-114">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 <span data-ttu-id="2792f-115">描述了 Windows 窗体数据绑定的不同类型的更改通知。</span><span class="sxs-lookup"><span data-stu-id="2792f-115">Describes different types of change notification for Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="2792f-116">如何：实现 INotifyPropertyChanged 接口</span><span class="sxs-lookup"><span data-stu-id="2792f-116">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 <span data-ttu-id="2792f-117">演示如何实现 <xref:System.ComponentModel.INotifyPropertyChanged> 接口。</span><span class="sxs-lookup"><span data-stu-id="2792f-117">Shows how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="2792f-118">该接口与属性在业务对象上更改的绑定控件通信</span><span class="sxs-lookup"><span data-stu-id="2792f-118">The interface  communicates to a bound control the property changes on a business object</span></span>  
  
 [<span data-ttu-id="2792f-119">如何：应用 PropertyNameChanged 模式</span><span class="sxs-lookup"><span data-stu-id="2792f-119">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 <span data-ttu-id="2792f-120">演示如何将应用*PropertyName*到 Windows 窗体用户控件的属性已更改模式。</span><span class="sxs-lookup"><span data-stu-id="2792f-120">Shows how to apply the *PropertyName*Changed pattern to properties of a Windows Forms user control.</span></span>  
  
 [<span data-ttu-id="2792f-121">如何：实现 ITypedList 接口</span><span class="sxs-lookup"><span data-stu-id="2792f-121">How to: Implement the ITypedList Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 <span data-ttu-id="2792f-122">演示如何通过实现 <xref:System.ComponentModel.ITypedList> 接口，启用可绑定列表的架构发现。</span><span class="sxs-lookup"><span data-stu-id="2792f-122">Shows how to enable discovery of the schema for a bindable list by implementing the <xref:System.ComponentModel.ITypedList> interface.</span></span>  
  
 [<span data-ttu-id="2792f-123">如何：实现 IListSource 接口</span><span class="sxs-lookup"><span data-stu-id="2792f-123">How to: Implement the IListSource Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 <span data-ttu-id="2792f-124">演示如何实现 <xref:System.ComponentModel.IListSource> 接口，以创建可绑定的类，其不实现 <xref:System.Collections.IList>，但提供其他位置的列表。</span><span class="sxs-lookup"><span data-stu-id="2792f-124">Shows how to implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class does not implement <xref:System.Collections.IList>, but provides a list from another location.</span></span>  
  
 [<span data-ttu-id="2792f-125">如何：确保绑定到同一数据源的多个控件保持同步</span><span class="sxs-lookup"><span data-stu-id="2792f-125">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 <span data-ttu-id="2792f-126">演示如何处理 <xref:System.Windows.Forms.BindingSource.BindingComplete> 事件，以确保所有绑定到数据源的控件保持同步。</span><span class="sxs-lookup"><span data-stu-id="2792f-126">Shows how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event to ensure all controls bound to a data source remain synchronized.</span></span>  
  
 [<span data-ttu-id="2792f-127">如何：确保子表中的选定行保持在正确的位置</span><span class="sxs-lookup"><span data-stu-id="2792f-127">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 <span data-ttu-id="2792f-128">演示如何确保在更改父表的字段时，选定的子表行不会更改。</span><span class="sxs-lookup"><span data-stu-id="2792f-128">Shows how to ensure the selected row of a child table does not change, when a change is made to a field of the parent table.</span></span>  
  
 <span data-ttu-id="2792f-129">另请参阅[与数据绑定相关的接口](http://msdn.microsoft.com/library/41e17s4b\(v=vs.110\))，[如何： 在 Windows 窗体中导航数据](http://msdn.microsoft.com/library/b63ha24w\(v=vs.110\))，[如何： 创建 Windows 窗体上的简单绑定控件](http://msdn.microsoft.com/library/sw223a62\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="2792f-129">Also see [Interfaces Related to Data Binding](http://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [How to: Navigate Data in Windows Forms](http://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [How to: Create a Simple-Bound Control on a Windows Form](http://msdn.microsoft.com/library/sw223a62\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2792f-130">参考</span><span class="sxs-lookup"><span data-stu-id="2792f-130">Reference</span></span>  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 <span data-ttu-id="2792f-131">描述表示可绑定组件和数据源之间的绑定的类。</span><span class="sxs-lookup"><span data-stu-id="2792f-131">Describes the class that represents the binding between a bindable component and a data source.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 <span data-ttu-id="2792f-132">描述用来封装数据源以绑定到控件的类。</span><span class="sxs-lookup"><span data-stu-id="2792f-132">Describes the class that encapsulates a data source for binding to controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2792f-133">相关章节</span><span class="sxs-lookup"><span data-stu-id="2792f-133">Related Sections</span></span>  
 [<span data-ttu-id="2792f-134">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="2792f-134">BindingSource Component</span></span>](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 <span data-ttu-id="2792f-135">包含演示如何使用 <xref:System.Windows.Forms.BindingSource> 组件的主题列表。</span><span class="sxs-lookup"><span data-stu-id="2792f-135">Contains a list of topics that demonstrate how to use the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="2792f-136">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="2792f-136">DataGridView Control</span></span>](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 <span data-ttu-id="2792f-137">提供演示如何使用可绑定的 datagrid 控件的主题列表。</span><span class="sxs-lookup"><span data-stu-id="2792f-137">Provides a list of topics that demonstrate how to use a bindable datagrid control.</span></span>  
  
 <span data-ttu-id="2792f-138">另请参阅[Visual Studio 中访问数据](/visualstudio/data-tools/accessing-data-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="2792f-138">Also see [Accessing Data in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span></span>
