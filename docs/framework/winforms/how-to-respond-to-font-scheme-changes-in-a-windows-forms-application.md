---
title: 如何：在 Windows 窗体应用程序中响应字体方案更改
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 2451885c673515eb6690b0784fd5bd22de629209
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "37071141"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>如何：在 Windows 窗体应用程序中响应字体方案更改
在 Windows 操作系统，用户可以更改系统范围的字体设置，以使显示的默认字体放大或缩小。 更改这些字体设置为有视觉障碍并需要更大的类型来读取其屏幕上的文本的用户至关重要。 你可以调整 Windows 窗体应用程序以通过增加或减少的大小的窗体和所有包含的文本的字体方案更改时对这些更改做出响应。 如果你想窗体以动态地适应字体大小的更改，你可以将代码添加到你的窗体。  
  
 通常情况下，Windows 窗体使用的默认字体是返回的字体<xref:Microsoft.Win32>命名空间调用`GetStockObject(DEFAULT_GUI_FONT)`。 此调用所返回的字体仅屏幕分辨率更改时进行更改。 下面的过程中所示，你的代码必须更改到的默认字体<xref:System.Drawing.SystemFonts.IconTitleFont%2A>的字体大小的更改进行响应。  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>若要使用的桌面的字体和响应字体方案更改  
  
1.  创建窗体中，并向其中添加所需的控件。 有关详细信息，请参阅[如何： 从命令行创建 Windows 窗体应用程序](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md)和[Windows 窗体上使用的控件](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)。  
  
2.  添加对的引用<xref:Microsoft.Win32>到你的代码的命名空间。  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  将以下代码添加到窗体必需的事件处理程序挂钩，并更改窗体所用的默认字体的构造函数。  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  实现的处理程序<xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>促使自动缩放窗体的事件时<xref:Microsoft.Win32.UserPreferenceCategory.Window>类别更改。  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  最后，实现的处理程序<xref:System.Windows.Forms.Form.FormClosing>分离的事件<xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>事件处理程序。  
  
     > [!IMPORTANT]
     > 不包括此代码将导致应用程序泄漏内存。  
  
     [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6.  编译并运行该代码。  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>若要手动更改在 Windows XP 中的字体方案  
  
1.  在 Windows 窗体应用程序运行时，右键单击 Windows 桌面上，然后选择**属性**从快捷菜单。  
  
2.  在**显示属性**对话框中，单击**外观**选项卡。  
  
3.  从**字体大小**下拉列表框中，选择新的字体大小。  
  
     你会注意到该窗体现在响应桌面字体方案中的运行时更改。 当用户更改之间**正常**，**大字体**，和**特大字体**，窗体更改字体，并正确缩放。  
  
## <a name="example"></a>示例  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 在此代码示例 constructer 包含调用`InitializeComponent`，这是定义当在 Visual Studio 中创建一个新的 Windows 窗体项目。 如果你在构建命令行上的应用程序，请删除此代码行。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [Windows 窗体中的自动缩放](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
