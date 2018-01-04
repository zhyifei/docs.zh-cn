---
title: "如何：将 ContextMenuStrip 与控件关联"
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
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7307af535dce39443b623e1fee4491dd48ffbd94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a>如何：将 ContextMenuStrip 与控件关联
创建控件和快捷菜单后，使用以下过程在用户右键单击控件时显示给定的快捷菜单。 这些过程将 <xref:System.Windows.Forms.ContextMenuStrip> 与 Windows 窗体和 <xref:System.Windows.Forms.ToolStrip> 控件相关联。  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a>将 ContextMenuStrip 与 Windows 窗体关联  
  
1.  将 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性设置为关联的 <xref:System.Windows.Forms.ContextMenuStrip> 的名称。  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a>将 ContextMenuStrip 与 ToolStrip 控件关联  
  
1.  将控件的 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 属性设置为关联的 <xref:System.Windows.Forms.ContextMenuStrip> 的名称。  
  
## <a name="example"></a>示例  
 下面的代码示例创建了 Windows 窗体和 <xref:System.Windows.Forms.ToolStrip>，并将不同的 <xref:System.Windows.Forms.ContextMenuStrip> 与其中每个控件关联。  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
 有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。  另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>  
 <xref:System.Windows.Forms.ToolStrip>  
 [如何：向 ContextMenuStrip 添加菜单项](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)  
 [ContextMenuStrip 控件](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
