---
title: 使用嵌套的 Graphics 容器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: ba6bba84100a0ddcc87894710a6d3099ab0ccff5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="using-nested-graphics-containers"></a>使用嵌套的 Graphics 容器
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 提供可用于临时替换或增加中的状态的一部分的容器<xref:System.Drawing.Graphics>对象。 通过调用创建容器<xref:System.Drawing.Graphics.BeginContainer%2A>方法<xref:System.Drawing.Graphics>对象。 你可以调用<xref:System.Drawing.Graphics.BeginContainer%2A>重复以形成嵌套的容器。 每次调用<xref:System.Drawing.Graphics.BeginContainer%2A>必须成对使用，通过调用<xref:System.Drawing.Graphics.EndContainer%2A>。  
  
## <a name="transformations-in-nested-containers"></a>嵌套容器中的转换  
 下面的示例创建<xref:System.Drawing.Graphics>对象和在其中容器<xref:System.Drawing.Graphics>对象。 世界变换<xref:System.Drawing.Graphics>对象是在 x 方向翻译 100 单元和 80 单位在 y 方向。 容器的世界转换是 30 度旋转。 这段代码将调用`DrawRectangle(pen, -60, -30, 120, 60)`两次。 首次调用<xref:System.Drawing.Graphics.DrawRectangle%2A>位于容器; 也就是说，调用是对的调用之间<xref:System.Drawing.Graphics.BeginContainer%2A>和<xref:System.Drawing.Graphics.EndContainer%2A>。 第二次调用<xref:System.Drawing.Graphics.DrawRectangle%2A>后调用<xref:System.Drawing.Graphics.EndContainer%2A>。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 在前面的代码中，在容器内从绘制的矩形转换首先按容器 （旋转） 的世界变换和的世界变换<xref:System.Drawing.Graphics>对象 （翻译）。 从容器外部绘制的矩形转换只能由的世界变换<xref:System.Drawing.Graphics>对象 （翻译）。 下图显示两个矩形。  
  
 ![嵌套容器](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## <a name="clipping-in-nested-containers"></a>嵌套容器中的剪辑  
 下面的示例演示如何嵌套的容器处理剪辑区域。 该代码创建<xref:System.Drawing.Graphics>对象和在其中容器<xref:System.Drawing.Graphics>对象。 剪辑区域<xref:System.Drawing.Graphics>对象是一个矩形，且容器的剪辑区域椭圆。 这段代码将两个调用<xref:System.Drawing.Graphics.DrawLine%2A>方法。 首次调用<xref:System.Drawing.Graphics.DrawLine%2A>位于容器和第二次调用<xref:System.Drawing.Graphics.DrawLine%2A>超出容器 (在调用后<xref:System.Drawing.Graphics.EndContainer%2A>)。 由两个剪辑区域相交处剪辑的第一行。 第二行剪切只能由的矩形的剪辑区域<xref:System.Drawing.Graphics>对象。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 下图显示两个裁剪后的行。  
  
 ![嵌套容器](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 如上面的示例所示，转换和剪辑区域可以累计嵌套容器中。 如果设置容器的世界变换和<xref:System.Drawing.Graphics>对象，这两种转换将应用于从绘制在容器内的项。 容器的转换将应用的第一、 和的转换<xref:System.Drawing.Graphics>将第二个应用对象。 如果设置容器的剪辑区域与<xref:System.Drawing.Graphics>对象，将由两个剪辑区域相交处剪切取自在容器内的项。  
  
## <a name="quality-settings-in-nested-containers"></a>嵌套容器中的质量设置  
 质量设置 (<xref:System.Drawing.Graphics.SmoothingMode%2A>， <xref:System.Drawing.Graphics.TextRenderingHint%2A>，等等) 中嵌套的容器不是累积的; 相反，容器的质量设置临时替换的质量设置<xref:System.Drawing.Graphics>对象。 当您创建新的容器时，该容器的质量设置是设置为默认值。 例如，假设你有<xref:System.Drawing.Graphics>平滑模式的对象<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>。 创建容器，容器中的平滑模式时，默认的平滑模式。 你可以自由地设置平滑模式的容器，并将根据你设置的模式绘制绘制在容器内的任何项目。 调用的后面绘制的项<xref:System.Drawing.Graphics.EndContainer%2A>将根据平滑模式绘制 (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>)，在调用前就位已<xref:System.Drawing.Graphics.BeginContainer%2A>。  
  
## <a name="several-layers-of-nested-containers"></a>多层嵌套容器  
 你并不局限于在一个容器<xref:System.Drawing.Graphics>对象。 可以创建的容器的序列，每个嵌套在前面，并且你可以指定世界变换、 剪辑区域和每个这些嵌套容器的质量设置。 如果调用一绘制的方法，可从最内部的容器中，将按顺序，从最内部的容器开始和结束与最外面的容器应用转换。 将所有的剪辑区域的交集剪切从最内部的容器内部绘制的项。  
  
 下面的示例创建<xref:System.Drawing.Graphics>对象并将其文本呈现提示设置为<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>。 该代码创建两个容器，嵌套在另一个。 外部容器的文本呈现提示设置为<xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>，并且内部的容器的文本呈现提示设置为<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>。 代码绘制三个字符串： 一个来自内部的容器，一个从外部的容器中，从一个<xref:System.Drawing.Graphics>对象本身。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 下图显示三个字符串。 从内部的容器和从绘制的字符串<xref:System.Drawing.Graphics>对象进行平滑处理通过抗锯齿功能。 从外部容器绘制的字符串不因为由抗锯齿平滑<xref:System.Drawing.Graphics.TextRenderingHint%2A>属性设置为<xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>。  
  
 ![嵌套容器](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Graphics>  
 [管理图形对象的状态](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)
