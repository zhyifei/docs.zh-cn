---
title: "如何：设置钢笔颜色"
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
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 452e88b4b41a22cc78f73e120e49468e4f4dad56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-color-of-a-pen"></a>如何：设置钢笔颜色
此示例将更改预先存在的颜色<xref:System.Drawing.Pen>对象  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   A<xref:System.Drawing.Pen>对象名为`myPen`。  
  
## <a name="robust-programming"></a>可靠编程  
 应调用<xref:System.Drawing.Pen.Dispose%2A>对对象所消耗的系统资源 (如<xref:System.Drawing.Pen>对象) 在完成使用它们后。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Pen>  
 [图形编程入门](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [如何：创建笔](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [使用笔绘制直线和形状](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [GDI+ 中的笔、直线和矩形](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
