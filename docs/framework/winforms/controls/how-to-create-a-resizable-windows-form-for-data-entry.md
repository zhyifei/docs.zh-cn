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
ms.openlocfilehash: aeab1b506b9ded4c3c2ab527f07a8655a44cad2b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72396026"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>如何：创建用于数据输入的大小可调的 Windows 窗体
良好的布局可以很好地响应其父窗体尺寸的更改。 可以使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件来安排窗体布局，从而以与窗体尺寸更改一致的方式调整和定位控件。 当控件内容的更改引起布局更改时，<xref:System.Windows.Forms.TableLayoutPanel> 控件也会很有用。 可以在 Visual Studio 环境中完成此过程所涵盖的进程。  另请参阅[演练：创建可根据数据输入需要调整大小的 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))。  
  
## <a name="example"></a>示例  
 下面的示例演示当用户调整窗体大小时，如何使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件构建响应良好的布局。 它还演示一个适合本地化的布局。  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [如何：设计非常适合本地化的 Windows 窗体布局](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
