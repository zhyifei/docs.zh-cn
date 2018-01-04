---
title: "如何：实现 IListSource 接口"
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
- data binding [Windows Forms], implementing
- IListSource interface
ms.assetid: 63ce27aa-2e23-4fbd-8228-0c1726f6c421
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2be4bdc923b894476747c69aca15ffa6f9b2c66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-the-ilistsource-interface"></a><span data-ttu-id="8c49c-102">如何：实现 IListSource 接口</span><span class="sxs-lookup"><span data-stu-id="8c49c-102">How to: Implement the IListSource Interface</span></span>
<span data-ttu-id="8c49c-103">实现<xref:System.ComponentModel.IListSource>接口可创建可绑定的类不实现<xref:System.Collections.IList>而是提供了另一个位置中的列表。</span><span class="sxs-lookup"><span data-stu-id="8c49c-103">Implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class that does not implement <xref:System.Collections.IList> but instead provides a list from another location.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c49c-104">示例</span><span class="sxs-lookup"><span data-stu-id="8c49c-104">Example</span></span>  
 <span data-ttu-id="8c49c-105">下面的代码示例演示如何实现<xref:System.ComponentModel.IListSource>接口。</span><span class="sxs-lookup"><span data-stu-id="8c49c-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.IListSource> interface.</span></span> <span data-ttu-id="8c49c-106">一个名为组件`EmployeeListSource`公开<xref:System.Collections.IList>用于数据绑定通过实现<xref:System.ComponentModel.IListSource.GetList%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="8c49c-106">A component named `EmployeeListSource` exposes an <xref:System.Collections.IList> for data binding by implementing the <xref:System.ComponentModel.IListSource.GetList%2A> method.</span></span>  
  
 [!code-csharp[System.ComponentModel.IListSource#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/EmployeeListSource.cs#1)]
 [!code-vb[System.ComponentModel.IListSource#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/EmployeeListSource.vb#1)]  
  
 [!code-csharp[System.ComponentModel.IListSource#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Employee.cs#10)]
 [!code-vb[System.ComponentModel.IListSource#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Employee.vb#10)]  
  
 [!code-csharp[System.ComponentModel.IListSource#100](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/BusinessObjectBase.cs#100)]
 [!code-vb[System.ComponentModel.IListSource#100](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/BusinessObjectBase.vb#100)]  
  
 [!code-csharp[System.ComponentModel.IListSource#1000](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Form1.cs#1000)]
 [!code-vb[System.ComponentModel.IListSource#1000](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Form1.vb#1000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8c49c-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="8c49c-107">Compiling the Code</span></span>  
 <span data-ttu-id="8c49c-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="8c49c-108">This example requires:</span></span>  
  
-   <span data-ttu-id="8c49c-109">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8c49c-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c49c-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c49c-110">See Also</span></span>  
 <xref:System.ComponentModel.IListSource>  
 <xref:System.ComponentModel.ITypedList>  
 <xref:System.ComponentModel.BindingList%601>  
 <xref:System.ComponentModel.IBindingList>  
 [<span data-ttu-id="8c49c-111">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="8c49c-111">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
