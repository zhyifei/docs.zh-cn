---
title: "如何：在 Windows 窗体上创建简单绑定控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b95892641000287f57840ec57cd65147b986829
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>如何：在 Windows 窗体上创建简单绑定控件
与*简单绑定*，你可以在控件中显示单个数据元素，如从数据集表中列的值。 可以将控件的任何属性的简单绑定到数据值。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-simple-bind-a-control"></a>简单绑定控件  
  
1.  连接到数据源。 有关详细信息，请参阅[连接到数据源](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)。  
  
2.  在表单中，选择控件，并显示**属性**窗口。  
  
3.  展开**(DataBindings)**属性。  
  
     最常绑定的属性将显示下**(DataBindings)**属性。 例如，在大多数控件，**文本**最经常绑定属性。  
  
4.  如果属性你想要绑定不是一个经常绑定的属性，单击**省略号**按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 在**（高级）**框，以显示**格式设置和高级绑定**对话框中的完整列表与该控件的属性。  
  
5.  选择你想要将绑定并单击下的下拉箭头的属性**绑定**。  
  
     此时将显示可用数据源的列表。  
  
6.  展开要绑定到的数据源，直到找到所需的单个数据元素。 例如，如果你正在绑定到数据集表中的列值，请展开该数据集的名称，然后展开表名以显示列名。  
  
7.  单击要绑定到的元素的名称。  
  
8.  如果你正在处理**格式设置和高级绑定**对话框中，单击**确定**以返回到**属性**窗口。  
  
9. 如果你想要将绑定控件的其他属性，请重复步骤 3 至 7。  
  
    > [!NOTE]
    >  因为简单绑定控件显示仅包含单个数据元素，它是非常典型导航逻辑包括在 Windows 窗体控件与简单绑定控件。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Binding>  
 [Windows 窗体数据绑定](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [数据绑定和 Windows 窗体](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
