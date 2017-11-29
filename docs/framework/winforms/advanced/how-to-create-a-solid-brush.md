---
title: "如何：创建实心画笔"
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
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01c07c132a703d6fd9401d9c191f5467667cc156
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-solid-brush"></a><span data-ttu-id="564c1-102">如何：创建实心画笔</span><span class="sxs-lookup"><span data-stu-id="564c1-102">How to: Create a Solid Brush</span></span>
<span data-ttu-id="564c1-103">此示例将创建<xref:System.Drawing.SolidBrush>对象，可以由用于<xref:System.Drawing.Graphics>用于填充形状的对象。</span><span class="sxs-lookup"><span data-stu-id="564c1-103">This example creates a <xref:System.Drawing.SolidBrush> object that can be used by a <xref:System.Drawing.Graphics> object for filling shapes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="564c1-104">示例</span><span class="sxs-lookup"><span data-stu-id="564c1-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="564c1-105">可靠编程</span><span class="sxs-lookup"><span data-stu-id="564c1-105">Robust Programming</span></span>  
 <span data-ttu-id="564c1-106">使用它们完后，应调用<xref:System.IDisposable.Dispose%2A>对对象所消耗的系统资源，例如画笔中的对象。</span><span class="sxs-lookup"><span data-stu-id="564c1-106">After you have finished using them, you should call <xref:System.IDisposable.Dispose%2A> on objects that consume system resources, such as brush objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564c1-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="564c1-107">See Also</span></span>  
 <xref:System.Drawing.SolidBrush>  
 <xref:System.Drawing.Brush>  
 [<span data-ttu-id="564c1-108">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="564c1-108">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="564c1-109">GDI+ 中的画笔和填充形状</span><span class="sxs-lookup"><span data-stu-id="564c1-109">Brushes and Filled Shapes in GDI+</span></span>](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)  
 [<span data-ttu-id="564c1-110">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="564c1-110">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
