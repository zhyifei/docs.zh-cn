---
title: "如何：绘制自定义虚线"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 770ce290b21f7d0094a487c30079063b79a7c08d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-custom-dashed-line"></a>如何：绘制自定义虚线
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]提供几种中列出的短划线样式<xref:System.Drawing.Drawing2D.DashStyle>枚举。 如果这些标准的短划线样式无法满足你的需求，你可以创建自定义的短划线图案。  
  
## <a name="example"></a>示例  
 若要绘制自定义虚线，放置在数组中的短划线和空白的长度，并将该数组指定为的值<xref:System.Drawing.Pen.DashPattern%2A>属性<xref:System.Drawing.Pen>对象。 下面的示例绘制自定义虚线基于阵列上`{5, 2, 15, 4}`。 如果数组的元素乘以钢笔的宽度为 5，则获取`{25, 10, 75, 20}`。 显示的短划线备用在 25 和 75，之间的长度和空间交替效果的长度介于 10 和 20 之间。  
  
 下图显示生成的虚线。 请注意，最终的短划线必须是少于 25 个单元，以便可以在结束行 （405，5）。  
  
 ![钢笔](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>编译代码  
 创建 Windows 窗体和处理该窗体<xref:System.Windows.Forms.Control.Paint>事件。 前面将代码粘贴到<xref:System.Windows.Forms.Control.Paint>事件处理程序。  
  
## <a name="see-also"></a>请参阅  
 [使用笔绘制直线和形状](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
