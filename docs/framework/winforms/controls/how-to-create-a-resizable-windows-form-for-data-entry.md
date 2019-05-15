---
title: 如何：创建可重设大小的 Windows 窗体以供输入数据
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
ms.openlocfilehash: 1b27c0e67aae1935c4216654d9f3ddf557719572
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588937"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>如何：创建可重设大小的 Windows 窗体以供输入数据
良好的布局可以很好地响应其父窗体尺寸的更改。 可以使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件来安排窗体布局，从而以与窗体尺寸更改一致的方式调整和定位控件。 当控件内容的更改引起布局更改时，<xref:System.Windows.Forms.TableLayoutPanel> 控件也会很有用。 可以在 Visual Studio 环境中完成此过程所涵盖的进程。  另请参阅[演练：创建数据输入可调整大小的 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))。  
  
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
- [如何：锚定和停靠在 TableLayoutPanel 控件中的子控件](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [如何：设计很好地响应本地化 Windows 窗体布局](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [Microsoft Windows 用户体验，用户界面开发人员和设计人员的官方指南。Redmond，WA:Microsoft Press，1999年。(USBN:0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
