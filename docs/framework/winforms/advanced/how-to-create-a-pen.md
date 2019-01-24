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
ms.openlocfilehash: b8a61e554ef58ca216050d34269e44355f7c1aaf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527440"
---
# <a name="how-to-create-a-pen"></a><span data-ttu-id="03d9e-102">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="03d9e-102">How to: Create a Pen</span></span>
<span data-ttu-id="03d9e-103">此示例将创建<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="03d9e-103">This example creates a <xref:System.Drawing.Pen> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03d9e-104">示例</span><span class="sxs-lookup"><span data-stu-id="03d9e-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="03d9e-105">可靠编程</span><span class="sxs-lookup"><span data-stu-id="03d9e-105">Robust Programming</span></span>  
 <span data-ttu-id="03d9e-106">使用对象占用系统资源，如完成后<xref:System.Drawing.Pen>对象，应调用<xref:System.Drawing.Pen.Dispose%2A>上它们。</span><span class="sxs-lookup"><span data-stu-id="03d9e-106">After you have finished using objects that consume system resources, such as <xref:System.Drawing.Pen> objects, you should call <xref:System.Drawing.Pen.Dispose%2A> on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d9e-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="03d9e-107">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="03d9e-108">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="03d9e-108">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="03d9e-109">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="03d9e-109">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
