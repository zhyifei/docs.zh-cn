---
title: "如何：使用 BindingSource 组件跨窗体共享绑定数据"
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
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 95fd7583e6d86aa84c53f6cee7056f1d631e948b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a>如何：使用 BindingSource 组件跨窗体共享绑定数据
使用 <xref:System.Windows.Forms.BindingSource> 组件可轻松跨窗体共享数据。 例如，你可能想要展示一个对数据源数据进行汇总的只读窗体和另一个包含有关数据源中当前所选项的详细信息的可编辑窗体。 此示例演示这种情况。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何跨窗体共享 <xref:System.Windows.Forms.BindingSource> 及其绑定数据。 在此示例中，共享的 <xref:System.Windows.Forms.BindingSource> 传递给子窗体的构造函数。 子窗体使用户可编辑主窗体中当前所选项的数据。  
  
> [!NOTE]
>  示例中处理了 <xref:System.Windows.Forms.BindingSource> 组件的 <xref:System.Windows.Forms.BindingSource.BindingComplete> 事件，以确保两个窗体保持同步。 若要深入了解进行此操作的原因，请参阅[如何：确保绑定到同一数据源的多个控件保持同步](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)。  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System、System.Windows.Forms、System.Drawing、System.Data 和 System.Xml 程序集的引用。  
  
 有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。  另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>另请参阅  
 [BindingSource 组件](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Windows 窗体数据绑定](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [如何：处理因数据绑定而发生的错误和异常](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
