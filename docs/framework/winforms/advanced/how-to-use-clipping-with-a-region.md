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
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="12061-102">如何：对区域使用剪辑</span><span class="sxs-lookup"><span data-stu-id="12061-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="12061-103">属性之一<xref:System.Drawing.Graphics>类是剪辑区域。</span><span class="sxs-lookup"><span data-stu-id="12061-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="12061-104">通过完成的所有绘图给定<xref:System.Drawing.Graphics>对象被限制为的剪辑区域<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="12061-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="12061-105">你可以通过调用设置的剪辑区域<xref:System.Drawing.Graphics.SetClip%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="12061-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12061-106">示例</span><span class="sxs-lookup"><span data-stu-id="12061-106">Example</span></span>  
 <span data-ttu-id="12061-107">下面的示例构造包含单个多边形的路径。</span><span class="sxs-lookup"><span data-stu-id="12061-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="12061-108">然后代码构造一个区域，基于该路径。</span><span class="sxs-lookup"><span data-stu-id="12061-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="12061-109">区域传递给<xref:System.Drawing.Graphics.SetClip%2A>方法<xref:System.Drawing.Graphics>绘制对象，以及然后两个字符串。</span><span class="sxs-lookup"><span data-stu-id="12061-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="12061-110">下图显示裁剪后的字符串。</span><span class="sxs-lookup"><span data-stu-id="12061-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="12061-111">![剪辑](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="12061-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="12061-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="12061-112">Compiling the Code</span></span>  
 <span data-ttu-id="12061-113">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。</span><span class="sxs-lookup"><span data-stu-id="12061-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12061-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="12061-114">See Also</span></span>  
 [<span data-ttu-id="12061-115">GDI+ 中的区域</span><span class="sxs-lookup"><span data-stu-id="12061-115">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [<span data-ttu-id="12061-116">使用区域</span><span class="sxs-lookup"><span data-stu-id="12061-116">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
