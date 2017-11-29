---
title: "如何：创建线性渐变"
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
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bbf3b1657a5a6b91ba88a0968b6b92d4e4bdbf0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-linear-gradient"></a>如何：创建线性渐变
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]提供水平线、 垂线、 对角线和线性渐变。 默认情况下中的线性渐变的颜色均匀地变化。 但是，以便的颜色更改非一致性方式可以自定义线性渐变。  
  
 下面的示例填充线条、 椭圆和一个具有水平线性渐变画笔的矩形。  
  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>构造函数接收四个自变量： 两个点以及两种颜色。 第一个点 （0，10） 程序与第一种颜色 （红色），并且第二个点 （200、 10） 与第二种颜色 （蓝色） 相关联。 如你所料的从绘制的线条 （0，10） 到 （200，10） 从红色为蓝色逐渐变成。  
  
 中的点 （50、 10） 和 200 （10） 的 10 并不重要。 重要的一点是两个点具有相同的第二个坐标 — 它们之间的连线是水平。 椭圆和矩形还逐渐从更改为蓝色，因为水平坐标将从 0 到 200 个的红色。  
  
 下图显示行、 椭圆和矩形。 请注意，颜色渐变本身可根据重复的水平坐标增加到 200 以上。  
  
 ![线性渐变](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")  
  
### <a name="to-use-horizontal-linear-gradients"></a>若要使用水平线性渐变  
  
-   将不透明的红色，并不透明蓝色分别作为第三个和第四个参数传递。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 在前面的示例中，颜色组件以线性方式更改当你从 0 的水平坐标移到 200 的水平坐标。 例如，其第一个坐标是介于 0 到 200 之间的中间值的点将具有是介于 0 和 255 之间的中间值蓝色分量。  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]允许你调整颜色因某条边的渐变到另的方式。 假设你想要创建一个渐变画笔，它从黑色将更改为红色根据下表。  
  
|水平坐标|RGB 组件|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 请注意，红色组件以半强度时，水平坐标是仅有 20%的从 0 到 200 个的方法。  
  
 下面的示例设置<xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A>属性<xref:System.Drawing.Drawing2D.LinearGradientBrush>将三个相对亮度与三个相对位置相关联的对象。 与上表中，一样 0.5 相对强度是与 0.2 的相对位置相关联。 该代码填充椭圆和一个具有渐变画笔的矩形。  
  
 下图显示得到的椭圆和矩形。  
  
 ![线性渐变](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")  
  
### <a name="to-customize-linear-gradients"></a>若要自定义线性渐变  
  
-   将不透明的黑色和不透明红分别作为第三个和第四个参数传递。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 在上面的示例的渐变是水平的;也就是说，当的颜色更改逐渐沿任何水平行移动。 你还可以定义垂直渐变和对角线渐变。  
  
 下面的示例将点 （0，0） 和 （200，100） 传递给<xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>构造函数。 蓝色关联 （0，0），并与关联绿色 （200，100）。 （带有钢笔的宽度 10） 的行和一个椭圆将使用线性渐变画笔填充。  
  
 下图显示行和椭圆。 请注意，椭圆更改中的颜色逐渐随着沿任何行，是类似于通过传递的行 （0，0） 和 （200，100）。  
  
 ![线性渐变](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")  
  
### <a name="to-create-diagonal-linear-gradients"></a>若要创建对角线方向线性渐变  
  
-   在不透明的蓝色和不透明绿色将作为第三个和第四个参数传递，分别。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>另请参阅  
 [使用渐变画笔填充形状](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
