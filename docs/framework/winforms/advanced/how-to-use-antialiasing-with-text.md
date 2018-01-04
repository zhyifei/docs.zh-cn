---
title: "如何：对文本使用抗锯齿效果"
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
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edd31ec5b9d94ac1791fb0f2a73522fdf4178627
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="20001-102">如何：对文本使用抗锯齿效果</span><span class="sxs-lookup"><span data-stu-id="20001-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="20001-103">*抗锯齿*指的是平滑的粗糙边缘绘制的图形和文本，以提高其外观或可读性。</span><span class="sxs-lookup"><span data-stu-id="20001-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="20001-104">通过托管[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]类，可以呈现高质量消除锯齿的文本，以及较低质量的文本。</span><span class="sxs-lookup"><span data-stu-id="20001-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="20001-105">通常情况下，呈现的质量越高采用更多的处理时间比较低质量呈现。</span><span class="sxs-lookup"><span data-stu-id="20001-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="20001-106">若要设置的文本质量级别，设置<xref:System.Drawing.Graphics.TextRenderingHint%2A>属性<xref:System.Drawing.Graphics>到的元素之一<xref:System.Drawing.Text.TextRenderingHint>枚举</span><span class="sxs-lookup"><span data-stu-id="20001-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="20001-107">示例</span><span class="sxs-lookup"><span data-stu-id="20001-107">Example</span></span>  
 <span data-ttu-id="20001-108">下面的代码示例绘制了两种不同的质量设置的文本。</span><span class="sxs-lookup"><span data-stu-id="20001-108">The following code example draws text with two different quality settings.</span></span>  
  
 <span data-ttu-id="20001-109">下图显示 cod 的输出示例代码。</span><span class="sxs-lookup"><span data-stu-id="20001-109">The following illustration shows the output of the cod example code.</span></span>  
  
 <span data-ttu-id="20001-110">![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="20001-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="20001-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="20001-111">Compiling the Code</span></span>  
 <span data-ttu-id="20001-112">前面的代码示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="20001-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20001-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="20001-113">See Also</span></span>  
 [<span data-ttu-id="20001-114">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="20001-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
