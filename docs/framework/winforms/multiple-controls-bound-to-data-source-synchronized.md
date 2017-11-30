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
ms.openlocfilehash: 2573f342530e59fa05e7f24342f251990b2ce47d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>如何：确保绑定到同一数据源的多个控件保持同步
通常当使用 Windows 窗体中的数据绑定时, 多个控件将绑定到同一数据源。 在某些情况下，可能需要进行额外的步骤，以确保控件的绑定的属性保持同步与彼此和数据源。 这些步骤是在两个情况下需要：  
  
-   如果数据源不实现<xref:System.ComponentModel.IBindingList>，并因此生成<xref:System.ComponentModel.IBindingList.ListChanged>类型的事件<xref:System.ComponentModel.ListChangedType.ItemChanged>。  
  
-   如果数据源实现<xref:System.ComponentModel.IEditableObject>。  
  
 在前一种情况，你可以使用<xref:System.Windows.Forms.BindingSource>将数据源绑定到控件。 在后一种情况，你使用<xref:System.Windows.Forms.BindingSource>并处理<xref:System.Windows.Forms.BindingSource.BindingComplete>事件并调用<xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A>上关联<xref:System.Windows.Forms.BindingManagerBase>。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何将三个控件绑定-两个文本框中控件和<xref:System.Windows.Forms.DataGridView>控件 — 到中的同一列<xref:System.Data.DataSet>使用<xref:System.Windows.Forms.BindingSource>组件。 此示例演示了如何处理<xref:System.Windows.Forms.BindingSource.BindingComplete>事件，并确保一个文本框中的文本值更改时，其他文本框和<xref:System.Windows.Forms.DataGridView>控件更新为正确的值。  
  
 该示例使用<xref:System.Windows.Forms.BindingSource>要绑定数据源和控件。 或者，你可以将控件绑定到数据源的直接并检索<xref:System.Windows.Forms.BindingManagerBase>从窗体的绑定<xref:System.Windows.Forms.Control.BindingContext%2A>，然后处理<xref:System.Windows.Forms.BindingManagerBase.BindingComplete>事件<xref:System.Windows.Forms.BindingManagerBase>。 如何执行此操作的示例，请参阅帮助页关于<xref:System.Windows.Forms.BindingManagerBase.BindingComplete>事件<xref:System.Windows.Forms.BindingManagerBase>。  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   此代码示例要求  
  
-   对 <xref:System><xref:System.Windows.Forms> 和 <xref:System.Drawing> 程序集的引用。  
  
-   窗体具有<xref:System.Windows.Forms.Form.Load>处理事件和调用`InitializeControlsAndDataSource`方法在示例中从窗体的<xref:System.Windows.Forms.Form.Load>事件处理程序。  
  
## <a name="see-also"></a>另请参阅  
 [如何：使用 BindingSource 组件跨窗体共享绑定数据](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [Windows 窗体数据绑定中的更改通知](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [与数据绑定相关的接口](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [Windows 窗体数据绑定](../../../docs/framework/winforms/windows-forms-data-binding.md)
