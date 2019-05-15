---
title: 如何：使用 BindingSource 在 Windows 窗体控件中反映数据源更新
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
ms.openlocfilehash: 9b3f3c53a74fa00c4e2c674fe6270a22e6e8cef5
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591457"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a>如何：使用 BindingSource 在 Windows 窗体控件中反映数据源更新
使用绑定数据的控件时，如果数据源不引发更改列表的事件，有时需要对数据源中的更改作出响应。 当使用 <xref:System.Windows.Forms.BindingSource> 组件将数据源绑定到 Windows 窗体控件时，可以通过调用 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 方法通知控件数据源已更改。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 方法通知绑定的控件有关数据源中的更新。  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [BindingSource 组件](bindingsource-component.md)
- [如何：将 Windows 窗体控件绑定到类型](how-to-bind-a-windows-forms-control-to-a-type.md)
