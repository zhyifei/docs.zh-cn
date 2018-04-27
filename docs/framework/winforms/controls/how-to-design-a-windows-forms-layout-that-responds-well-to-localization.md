---
title: 如何：设计适合本地化的 Windows 窗体布局
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3833c147720f9a223fab6e69afeb819832bd98f2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>如何：设计适合本地化的 Windows 窗体布局
创建可供进行本地化的窗体极大地加速了国际市场的开发。 可以使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件实现在控件因 <xref:System.Windows.Forms.Control.Text%2A> 属性值更改而调整大小时正常响应的布局。  
  
## <a name="example"></a>示例  
 此窗体演示如何创建在将显示的字符串值翻译成其它语言时按比例进行调整的布局。 这一翻译过程称为*本地化*。 有关详细信息，请参阅[本地化](../../../../docs/standard/globalization-localization/localization.md)。  
  
 Visual Studio 中对此任务提供广泛支持。  另请参阅[演练：创建可根据本地化需要调整比例的布局](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\))。  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [如何：在 TableLayoutPanel 控件中对齐和拉伸控件](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))  
  
2.  [演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))  
  
3.  [如何：在 TableLayoutPanel 控件中跨行和跨列](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))  
  
4.  [如何：在 TableLayoutPanel 控件中编辑行和列](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))  
  
5.  [演练：使用 Windows 窗体控件上的智能标记执行常规任务](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))  
  
6.  [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
7.  [演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))  
  
8.  [如何：使用 AutoSize 属性和 TableLayoutPanel 控件支持对 Windows 窗体的本地化](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))  
  
9. [演练：创建可根据数据输入需要调整大小的 Windows 窗体](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
 为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。  另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [本地化](../../../../docs/standard/globalization-localization/localization.md)
