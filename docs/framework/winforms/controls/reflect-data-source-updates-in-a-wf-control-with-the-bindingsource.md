---
title: 用 BindingSource 反射控件中的数据源更新
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: f98296b477dbb674cdbdbd8d03e291dd6ca0c8a3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742434"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a><span data-ttu-id="d947f-102">如何：使用 BindingSource 在 Windows 窗体控件中反映数据源更新</span><span class="sxs-lookup"><span data-stu-id="d947f-102">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>
<span data-ttu-id="d947f-103">使用绑定数据的控件时，如果数据源不引发更改列表的事件，有时需要对数据源中的更改作出响应。</span><span class="sxs-lookup"><span data-stu-id="d947f-103">When you use data-bound controls, you sometimes have to respond to changes in the data source when the data source does not raise list-changed events.</span></span> <span data-ttu-id="d947f-104">当使用 <xref:System.Windows.Forms.BindingSource> 组件将数据源绑定到 Windows 窗体控件时，可以通过调用 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 方法通知控件数据源已更改。</span><span class="sxs-lookup"><span data-stu-id="d947f-104">When you use the <xref:System.Windows.Forms.BindingSource> component to bind your data source to a Windows Forms control, you can notify the control that your data source has changed by calling the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d947f-105">示例</span><span class="sxs-lookup"><span data-stu-id="d947f-105">Example</span></span>  
 <span data-ttu-id="d947f-106">下面的代码示例演示如何使用 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 方法通知绑定的控件有关数据源中的更新。</span><span class="sxs-lookup"><span data-stu-id="d947f-106">The following code example demonstrates using the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method to notify a bound control about an update in the data source.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d947f-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="d947f-107">Compiling the Code</span></span>  
 <span data-ttu-id="d947f-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d947f-108">This example requires:</span></span>  
  
- <span data-ttu-id="d947f-109">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d947f-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d947f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d947f-110">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d947f-111">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="d947f-111">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="d947f-112">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="d947f-112">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
