---
title: 如何：将控件添加到选项卡页
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 9806583fda60f1cb8a5ef2d97f42eba158593f61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322714"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>如何：将控件添加到选项卡页
可以使用 Windows 窗体<xref:System.Windows.Forms.TabControl>有条理的方式显示其他控件。 以下过程说明如何将按钮添加到第一个选项卡。有关将图标添加到标签部分选项卡页的信息，请参阅[如何：更改 Windows 窗体 TabControl 的外观](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)。  
  
### <a name="to-add-a-control-programmatically"></a>若要以编程方式添加控件  
  
1. 使用<xref:System.Windows.Forms.Control.ControlCollection.Add%2A>方法返回的集合<xref:System.Windows.Forms.Control.Controls%2A>属性的<xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>请参阅

- [TabControl 控件](tabcontrol-control-windows-forms.md)
- [TabControl 控件概述](tabcontrol-control-overview-windows-forms.md)
- [如何：更改 Windows 窗体 TabControl 的外观](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [如何：禁用选项卡页](how-to-disable-tab-pages.md)
- [如何：添加和删除使用 Windows 窗体 TabControl 的选项卡](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
