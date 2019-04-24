---
title: 如何：创建钢笔
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: 69fe6157c710ae63df9dbf391a5d355d1c3f9765
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148104"
---
# <a name="how-to-create-a-pen"></a>如何：创建钢笔
此示例将创建<xref:System.Drawing.Pen>对象。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a>可靠编程  
 使用对象占用系统资源，如完成后<xref:System.Drawing.Pen>对象，应调用<xref:System.Drawing.Pen.Dispose%2A>上它们。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Drawing.Pen>
- [图形编程入门](getting-started-with-graphics-programming.md)
- [GDI+ 中的笔、直线和矩形](pens-lines-and-rectangles-in-gdi.md)
