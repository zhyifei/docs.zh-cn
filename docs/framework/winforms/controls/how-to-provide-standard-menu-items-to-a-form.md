---
title: 如何：向窗体提供标准菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: befff7b2eceb37b49c4d1263f46bf93775d432c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564002"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a>如何：向窗体提供标准菜单项
可使用 <xref:System.Windows.Forms.MenuStrip> 控件向窗体提供标准菜单。  
  
 没有对此功能在 Visual Studio 中的广泛支持。  
  
 另请参阅[演练：向窗体提供标准菜单项](walkthrough-providing-standard-menu-items-to-a-form.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例演示了如何使用 <xref:System.Windows.Forms.MenuStrip> 控件创建带有标准菜单的窗体。 <xref:System.Windows.Forms.StatusStrip> 控件中将显示菜单项选择。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
 Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。  另请参阅[如何：编译和运行完整的 Windows 窗体代码示例使用 Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [MenuStrip 控件](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
