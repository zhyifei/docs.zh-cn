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
ms.openlocfilehash: d7fb7c11a69cae69210dd2eece3336bc40c505c7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711975"
---
# <a name="how-to-create-a-solid-brush"></a><span data-ttu-id="3dbe1-102">如何：创建实心画笔</span><span class="sxs-lookup"><span data-stu-id="3dbe1-102">How to: Create a Solid Brush</span></span>
<span data-ttu-id="3dbe1-103">此示例将创建<xref:System.Drawing.SolidBrush>对象，它可由<xref:System.Drawing.Graphics>用于填充形状的对象。</span><span class="sxs-lookup"><span data-stu-id="3dbe1-103">This example creates a <xref:System.Drawing.SolidBrush> object that can be used by a <xref:System.Drawing.Graphics> object for filling shapes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dbe1-104">示例</span><span class="sxs-lookup"><span data-stu-id="3dbe1-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="3dbe1-105">可靠编程</span><span class="sxs-lookup"><span data-stu-id="3dbe1-105">Robust Programming</span></span>  
 <span data-ttu-id="3dbe1-106">使用它们完成后，应调用<xref:System.IDisposable.Dispose%2A>占用系统资源，例如画笔对象的对象。</span><span class="sxs-lookup"><span data-stu-id="3dbe1-106">After you have finished using them, you should call <xref:System.IDisposable.Dispose%2A> on objects that consume system resources, such as brush objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dbe1-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dbe1-107">See also</span></span>
- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="3dbe1-108">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="3dbe1-108">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="3dbe1-109">GDI+ 中的画笔和填充形状</span><span class="sxs-lookup"><span data-stu-id="3dbe1-109">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
- [<span data-ttu-id="3dbe1-110">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="3dbe1-110">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
