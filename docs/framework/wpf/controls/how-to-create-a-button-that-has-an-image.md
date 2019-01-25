---
title: 如何：创建包含图像的按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: cfebe53047531ecddde42a3a0596dfd949629ecd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682043"
---
# <a name="how-to-create-a-button-that-has-an-image"></a>如何：创建包含图像的按钮
此示例演示如何上包含一个图像<xref:System.Windows.Controls.Button>。  
  
## <a name="example"></a>示例  
 下面的示例创建两个<xref:System.Windows.Controls.Button>控件。 一个<xref:System.Windows.Controls.Button>包含文本，另一个包含图像。 映像是在一个名为数据，这是该示例的项目文件夹的子文件夹中。 当用户单击<xref:System.Windows.Controls.Button>具有图像、 背景和其他文本<xref:System.Windows.Controls.Button>更改。  
  
 此示例将创建<xref:System.Windows.Controls.Button>通过使用标记控制，但使用代码来编写<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序。  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>请参阅
- [控件](../../../../docs/framework/wpf/controls/index.md)
- [控件库](../../../../docs/framework/wpf/controls/control-library.md)
