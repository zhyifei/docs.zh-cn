---
title: 如何：对区域使用剪辑
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: bfc40d985ec12a30b73935ace7ef034aadbd5385
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522091"
---
# <a name="how-to-use-clipping-with-a-region"></a>如何：对区域使用剪辑
属性之一<xref:System.Drawing.Graphics>类是剪辑区域。 通过完成的所有绘图给定<xref:System.Drawing.Graphics>对象被限制为的剪辑区域<xref:System.Drawing.Graphics>对象。 你可以通过调用设置的剪辑区域<xref:System.Drawing.Graphics.SetClip%2A>方法。  
  
## <a name="example"></a>示例  
 下面的示例构造包含单个多边形的路径。 然后代码构造一个区域，基于该路径。 区域传递给<xref:System.Drawing.Graphics.SetClip%2A>方法<xref:System.Drawing.Graphics>绘制对象，以及然后两个字符串。  
  
 下图显示裁剪后的字符串。  
  
 ![剪辑](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。  
  
## <a name="see-also"></a>请参阅  
 [GDI+ 中的区域](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [使用区域](../../../../docs/framework/winforms/advanced/using-regions.md)
