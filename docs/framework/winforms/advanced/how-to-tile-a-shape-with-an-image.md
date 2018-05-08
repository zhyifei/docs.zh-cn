---
title: 如何：在形状中平铺图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: 0905f29b0f74c72979e252cf94e677d1c7e0525d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-tile-a-shape-with-an-image"></a>如何：在形状中平铺图像
就像磁贴可以彼此以覆盖层相邻放置，可以将矩形映像彼此相邻放置于填充 （磁贴） 形状。 若要磁贴形状的内部，使用纹理画笔。 构造时<xref:System.Drawing.TextureBrush>对象，将传递给构造函数的自变量之一为<xref:System.Drawing.Image>对象。 当你使用的纹理画笔绘制形状的内部时，形状填充使用此映像的重复副本。  
  
 包装模式属性<xref:System.Drawing.TextureBrush>对象确定如何映像是面向随着矩形网格中重复。 您可以进行所有磁贴在网格中的具有相同的方向，也可以从一个网格位置到下一个翻转的图像。 翻转可以水平、 垂直或两者。 下面的示例演示使用不同类型的翻转平铺。  
  
### <a name="to-tile-an-image"></a>平铺图像  
  
-   此示例使用以下 75 × 75 图像平铺 200 × 200 的矩形。  
  
 ![磁贴 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")  
  
-   下图显示如何在该矩形平铺与映像。 请注意，所有图块具有相同的方向;没有翻转。  
  
 ![磁贴 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>若要水平时平铺翻转图像  
  
-   此示例使用相同的 75 × 75 图像以填充 200 × 200 矩形。 设置环绕模式为水平翻转图像。 下图显示如何在该矩形平铺与映像。 请注意当你从一个磁贴移动到给定行中下一步，水平翻转图像。  
  
 ![磁贴 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>若要垂直时平铺翻转图像  
  
-   此示例使用相同的 75 × 75 图像以填充 200 × 200 矩形。 设置环绕模式为垂直翻转图像。  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>平铺时水平和垂直翻转图像  
  
-   此示例使用相同的 75 × 75 图像平铺 200 × 200 的矩形。 设置环绕模式为水平和垂直翻转图像。 下图显示如何在该矩形平铺的映像。 请注意，当您从一个磁贴移动到给定行中下一步，水平翻转图像，则但当你从一个磁贴移动到给定列中下一步，垂直翻转图像。  
  
 ![磁贴 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>请参阅  
 [使用画笔填充形状](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
