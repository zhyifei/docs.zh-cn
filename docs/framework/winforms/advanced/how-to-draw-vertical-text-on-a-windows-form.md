---
title: "如何：在 Windows 窗体上绘制垂直文本"
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
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56feadd3bb5300376a16cc1d06d9af73ad77b565
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="6044b-102">如何：在 Windows 窗体上绘制垂直文本</span><span class="sxs-lookup"><span data-stu-id="6044b-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="6044b-103">下面的代码示例演示如何使用窗体上绘制垂直文本<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>。</span><span class="sxs-lookup"><span data-stu-id="6044b-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6044b-104">示例</span><span class="sxs-lookup"><span data-stu-id="6044b-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6044b-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="6044b-105">Compiling the Code</span></span>  
 <span data-ttu-id="6044b-106">无法调用此方法中<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6044b-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="6044b-107">不会重新绘制的内容的绘制，如果窗体调整大小或另一种形式被遮盖。</span><span class="sxs-lookup"><span data-stu-id="6044b-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="6044b-108">若要使你自动重绘的内容，则应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="6044b-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6044b-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="6044b-109">Robust Programming</span></span>  
 <span data-ttu-id="6044b-110">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="6044b-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="6044b-111">未安装 Arial 字体。</span><span class="sxs-lookup"><span data-stu-id="6044b-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6044b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6044b-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="6044b-113">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="6044b-113">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="6044b-114">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="6044b-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
