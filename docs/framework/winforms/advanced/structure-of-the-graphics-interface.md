---
title: "图形界面的结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43bd899a1dd53dc8cdae4f81e90b1aa74c29cb67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="structure-of-the-graphics-interface"></a>图形界面的结构
托管的类接口[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]包含大约 60 个类、 50 枚举和 8 个结构。 <xref:System.Drawing.Graphics>类的核心是[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]功能; 它是实际绘制线条、 曲线、 图形、 图像和文本的类。  
  
## <a name="important-classes"></a>重要的类  
 许多类可一起与<xref:System.Drawing.Graphics>类。 例如，<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象，包含要绘制的行的属性 （颜色、 宽度、 短划线样式和 like） 属性。 <xref:System.Drawing.Graphics.FillRectangle%2A>方法可以接收指向的指针<xref:System.Drawing.Drawing2D.LinearGradientBrush>对象，适用于<xref:System.Drawing.Graphics>对象填充渐变的颜色的矩形。 <xref:System.Drawing.Font>和<xref:System.Drawing.StringFormat>对象影响方式<xref:System.Drawing.Graphics>对象绘制文本。 A<xref:System.Drawing.Drawing2D.Matrix>对象存储和操作的世界变换<xref:System.Drawing.Graphics>对象，用于旋转、 缩放和翻转图像。  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]提供多个结构 (例如， <xref:System.Drawing.Rectangle>， <xref:System.Drawing.Point>，和<xref:System.Drawing.Size>) 用于组织图形数据。 此外，某些类充当主要结构化的数据类型。 例如，<xref:System.Drawing.Imaging.BitmapData>类是帮助器<xref:System.Drawing.Bitmap>类，与<xref:System.Drawing.Drawing2D.PathData>类是帮助器<xref:System.Drawing.Drawing2D.GraphicsPath>类。  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]定义了几种枚举，它们是相关的常数的集合。 例如，<xref:System.Drawing.Drawing2D.LineJoin>枚举包含元素<xref:System.Drawing.Drawing2D.LineJoin.Bevel>， <xref:System.Drawing.Drawing2D.LineJoin.Miter>，和<xref:System.Drawing.Drawing2D.LineJoin.Round>，它指定可用于联接两条线的样式。  
  
## <a name="see-also"></a>请参阅  
 [图形概述](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [关于 GDI+ 托管代码](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [使用托管图形类](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
