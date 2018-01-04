---
title: "如何：确保绑定到同一数据源的多个控件保持同步"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 227ad36e87c3deceb7fefe3cd19013fc8e76c686
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a><span data-ttu-id="d1a16-102">如何：确保绑定到同一数据源的多个控件保持同步</span><span class="sxs-lookup"><span data-stu-id="d1a16-102">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>
<span data-ttu-id="d1a16-103">通常当使用 Windows 窗体中的数据绑定时, 多个控件将绑定到同一数据源。</span><span class="sxs-lookup"><span data-stu-id="d1a16-103">Oftentimes when working with data binding in Windows Forms, multiple controls are bound to the same data source.</span></span> <span data-ttu-id="d1a16-104">在某些情况下，可能需要进行额外的步骤，以确保控件的绑定的属性保持同步与彼此和数据源。</span><span class="sxs-lookup"><span data-stu-id="d1a16-104">In some cases, it may be necessary to take extra steps to ensure that the bound properties of the controls remain synchronized with each other and the data source.</span></span> <span data-ttu-id="d1a16-105">这些步骤是在两个情况下需要：</span><span class="sxs-lookup"><span data-stu-id="d1a16-105">These steps are necessary in two situations:</span></span>  
  
-   <span data-ttu-id="d1a16-106">如果数据源不实现<xref:System.ComponentModel.IBindingList>，并因此生成<xref:System.ComponentModel.IBindingList.ListChanged>类型的事件<xref:System.ComponentModel.ListChangedType.ItemChanged>。</span><span class="sxs-lookup"><span data-stu-id="d1a16-106">If the data source does not implement <xref:System.ComponentModel.IBindingList>, and therefore generate <xref:System.ComponentModel.IBindingList.ListChanged> events of type <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span></span>  
  
-   <span data-ttu-id="d1a16-107">如果数据源实现<xref:System.ComponentModel.IEditableObject>。</span><span class="sxs-lookup"><span data-stu-id="d1a16-107">If the data source implements <xref:System.ComponentModel.IEditableObject>.</span></span>  
  
 <span data-ttu-id="d1a16-108">在前一种情况，你可以使用<xref:System.Windows.Forms.BindingSource>将数据源绑定到控件。</span><span class="sxs-lookup"><span data-stu-id="d1a16-108">In the former case, you can use a <xref:System.Windows.Forms.BindingSource> to bind the data source to the controls.</span></span> <span data-ttu-id="d1a16-109">在后一种情况，你使用<xref:System.Windows.Forms.BindingSource>并处理<xref:System.Windows.Forms.BindingSource.BindingComplete>事件并调用<xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A>上关联<xref:System.Windows.Forms.BindingManagerBase>。</span><span class="sxs-lookup"><span data-stu-id="d1a16-109">In the latter case, you use a <xref:System.Windows.Forms.BindingSource> and handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and call <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> on the associated <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1a16-110">示例</span><span class="sxs-lookup"><span data-stu-id="d1a16-110">Example</span></span>  
 <span data-ttu-id="d1a16-111">下面的代码示例演示如何将三个控件绑定-两个文本框中控件和<xref:System.Windows.Forms.DataGridView>控件 — 到中的同一列<xref:System.Data.DataSet>使用<xref:System.Windows.Forms.BindingSource>组件。</span><span class="sxs-lookup"><span data-stu-id="d1a16-111">The following code example demonstrates how to bind three controls—two text-box controls and a <xref:System.Windows.Forms.DataGridView> control—to the same column in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="d1a16-112">此示例演示了如何处理<xref:System.Windows.Forms.BindingSource.BindingComplete>事件，并确保一个文本框中的文本值更改时，其他文本框和<xref:System.Windows.Forms.DataGridView>控件更新为正确的值。</span><span class="sxs-lookup"><span data-stu-id="d1a16-112">This example demonstrates how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and ensure that when the text value of one text box is changed, the additional text box and the <xref:System.Windows.Forms.DataGridView> control are updated with the correct value.</span></span>  
  
 <span data-ttu-id="d1a16-113">该示例使用<xref:System.Windows.Forms.BindingSource>要绑定数据源和控件。</span><span class="sxs-lookup"><span data-stu-id="d1a16-113">The example uses a <xref:System.Windows.Forms.BindingSource> to bind the data source and the controls.</span></span> <span data-ttu-id="d1a16-114">或者，你可以将控件绑定到数据源的直接并检索<xref:System.Windows.Forms.BindingManagerBase>从窗体的绑定<xref:System.Windows.Forms.Control.BindingContext%2A>，然后处理<xref:System.Windows.Forms.BindingManagerBase.BindingComplete>事件<xref:System.Windows.Forms.BindingManagerBase>。</span><span class="sxs-lookup"><span data-stu-id="d1a16-114">Alternatively, you can bind the controls directly to the data source and retrieve the <xref:System.Windows.Forms.BindingManagerBase> for the binding from the form's <xref:System.Windows.Forms.Control.BindingContext%2A> and then handle the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event for the <xref:System.Windows.Forms.BindingManagerBase>.</span></span> <span data-ttu-id="d1a16-115">如何执行此操作的示例，请参阅帮助页关于<xref:System.Windows.Forms.BindingManagerBase.BindingComplete>事件<xref:System.Windows.Forms.BindingManagerBase>。</span><span class="sxs-lookup"><span data-stu-id="d1a16-115">For an example of how to do this, see the Help page about the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event of <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d1a16-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="d1a16-116">Compiling the Code</span></span>  
  
-   <span data-ttu-id="d1a16-117">此代码示例要求</span><span class="sxs-lookup"><span data-stu-id="d1a16-117">This code example requires</span></span>  
  
-   <span data-ttu-id="d1a16-118">对 <xref:System><xref:System.Windows.Forms> 和 <xref:System.Drawing> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d1a16-118">References to the <xref:System>, <xref:System.Windows.Forms>, and <xref:System.Drawing> assemblies.</span></span>  
  
-   <span data-ttu-id="d1a16-119">窗体具有<xref:System.Windows.Forms.Form.Load>处理事件和调用`InitializeControlsAndDataSource`方法在示例中从窗体的<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d1a16-119">A form with the <xref:System.Windows.Forms.Form.Load> event handled and a call to the `InitializeControlsAndDataSource` method in the example from the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a16-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1a16-120">See Also</span></span>  
 [<span data-ttu-id="d1a16-121">如何：使用 BindingSource 组件跨窗体共享绑定数据</span><span class="sxs-lookup"><span data-stu-id="d1a16-121">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [<span data-ttu-id="d1a16-122">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="d1a16-122">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="d1a16-123">与数据绑定相关的接口</span><span class="sxs-lookup"><span data-stu-id="d1a16-123">Interfaces Related to Data Binding</span></span>](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [<span data-ttu-id="d1a16-124">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="d1a16-124">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
