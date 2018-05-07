---
title: 如何：将控件锁定到 Windows 窗体
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: f05da53f134f13bf5edbbe7ab8c5973f79bbca4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-lock-controls-to-windows-forms"></a>如何：将控件锁定到 Windows 窗体
设计 Windows 应用程序的用户界面 (UI)，便可锁定控件后它们正确定位，以便不会无意中移动，或调整其大小设置其他属性时。  
  
 此外，你可以锁定和解锁所有窗体的控件，这将很多控件与窗体的有用，或可以解锁单独的控件。 一旦你已放置所有控件放置在所需窗体上，将其锁定所有的位置，以防止错误的移动。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-lock-a-control"></a>要锁定控件  
  
1.  在**属性**窗口中，单击**锁定**属性并选择`true`。 （双击名称切换属性设置。）  
  
     或者，右击该控件并选择**锁定控件**。  
  
    > [!NOTE]
    >  锁定控件可以防止它们设计图面上拖动到新的大小或位置。 但是，你仍可以更改的大小或通过控件的位置**属性**窗口或代码中。  
  
### <a name="to-lock-all-the-controls-on-a-form"></a>若要锁定窗体上的所有控件  
  
1.  从**格式**菜单上，选择**锁定控件**。  
  
    > [!NOTE]
    >  此命令锁定窗体的大小，因为窗体是控件。  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a>若要解锁所有锁定窗体上的控件  
  
1.  从**格式**菜单上，选择**锁定控件**。  
  
     窗体上的所有以前锁定的控件现解锁。  
  
### <a name="to-unlock-locked-controls-individually"></a>若要单独解锁锁定的控件  
  
1.  在**属性**窗口中，单击**锁定**属性并选择`false`。 （双击名称切换属性设置。）  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [标记各个 Windows 窗体控件并创建它们的快捷键](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [按功能列出的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
