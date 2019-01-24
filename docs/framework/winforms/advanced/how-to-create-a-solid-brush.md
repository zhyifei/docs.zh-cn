---
title: 如何：创建实心画笔
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: 0943bd1d5e05a1d726f0f6c55e372b9ff70cc4ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632265"
---
# <a name="how-to-create-a-solid-brush"></a>如何：创建实心画笔
此示例将创建<xref:System.Drawing.SolidBrush>对象，它可由<xref:System.Drawing.Graphics>用于填充形状的对象。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a>可靠编程  
 使用它们完成后，应调用<xref:System.IDisposable.Dispose%2A>占用系统资源，例如画笔对象的对象。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [图形编程入门](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [GDI+ 中的画笔和填充形状](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)
- [使用画笔填充形状](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
