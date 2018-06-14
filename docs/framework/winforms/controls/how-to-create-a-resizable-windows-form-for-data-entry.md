---
title: 如何：创建用于数据输入的大小可调的 Windows 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: a7768b3c6be10373e742cbeea0028d1aee0b261d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531786"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>如何：创建用于数据输入的大小可调的 Windows 窗体
良好的布局可以很好地响应其父窗体尺寸的更改。 可以使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件来安排窗体布局，从而以与窗体尺寸更改一致的方式调整和定位控件。 当控件内容的更改引起布局更改时，<xref:System.Windows.Forms.TableLayoutPanel> 控件也会很有用。 可以在 Visual Studio 环境中完成此过程所涵盖的进程。  另请参阅[演练：创建可根据数据输入需要调整大小的 Windows 窗体](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))。  
  
## <a name="example"></a>示例  
 下面的示例演示当用户调整窗体大小时，如何使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件构建响应良好的布局。 它还演示一个适合本地化的布局。  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
 为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。  另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [如何：设计非常适合本地化的 Windows 窗体布局](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [Microsoft Windows 用户体验，用户界面开发人员和设计人员的官方指南。Redmond, WA: Microsoft Press, 1999.(USBN: 0-7356-0566-1)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)
