---
title: "如何：创建特定形状的 Windows 窗体"
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
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 981256c2447a53aef8e1ea676db38ce693d1337e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="4f137-102">如何：创建特定形状的 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="4f137-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="4f137-103">此示例使窗体调整大小时处理该窗体是椭圆形状。</span><span class="sxs-lookup"><span data-stu-id="4f137-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f137-104">示例</span><span class="sxs-lookup"><span data-stu-id="4f137-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f137-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="4f137-105">Compiling the Code</span></span>  
 <span data-ttu-id="4f137-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="4f137-106">This example requires:</span></span>  
  
-   <span data-ttu-id="4f137-107">对 <xref:System.Windows.Forms> 和 <xref:System.Drawing> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="4f137-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="4f137-108">此示例替代<xref:System.Windows.Forms.Control.OnPaint%2A>方法用于更改窗体的形状。</span><span class="sxs-lookup"><span data-stu-id="4f137-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="4f137-109">若要使用此代码，将复制的方法声明，以及在方法内的绘制代码。</span><span class="sxs-lookup"><span data-stu-id="4f137-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f137-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f137-110">See Also</span></span>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Region>  
 <xref:System.Drawing>  
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>  
 <xref:System.Windows.Forms.Control.Region%2A>  
 [<span data-ttu-id="4f137-111">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="4f137-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
