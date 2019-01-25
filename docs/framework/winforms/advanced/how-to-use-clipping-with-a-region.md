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
ms.openlocfilehash: 5482218a8d6310ce49a1f9f5f02b3b8e36c1fd90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590651"
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="e927c-102">如何：对区域使用剪辑</span><span class="sxs-lookup"><span data-stu-id="e927c-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="e927c-103">属性之一<xref:System.Drawing.Graphics>类是剪辑区域。</span><span class="sxs-lookup"><span data-stu-id="e927c-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="e927c-104">通过完成的所有绘制给定<xref:System.Drawing.Graphics>对象被限制为的剪辑区域<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="e927c-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e927c-105">可以通过调用设置的剪辑区域<xref:System.Drawing.Graphics.SetClip%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e927c-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e927c-106">示例</span><span class="sxs-lookup"><span data-stu-id="e927c-106">Example</span></span>  
 <span data-ttu-id="e927c-107">下面的示例构造包含单个多边形的路径。</span><span class="sxs-lookup"><span data-stu-id="e927c-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="e927c-108">然后，代码构造的区域，根据该路径。</span><span class="sxs-lookup"><span data-stu-id="e927c-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="e927c-109">在区域传递给<xref:System.Drawing.Graphics.SetClip%2A>方法的<xref:System.Drawing.Graphics>绘制对象，然后两个字符串。</span><span class="sxs-lookup"><span data-stu-id="e927c-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="e927c-110">下图显示了裁剪后的字符串。</span><span class="sxs-lookup"><span data-stu-id="e927c-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="e927c-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="e927c-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e927c-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="e927c-112">Compiling the Code</span></span>  
 <span data-ttu-id="e927c-113">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。</span><span class="sxs-lookup"><span data-stu-id="e927c-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e927c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e927c-114">See also</span></span>
- [<span data-ttu-id="e927c-115">GDI+ 中的区域</span><span class="sxs-lookup"><span data-stu-id="e927c-115">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)
- [<span data-ttu-id="e927c-116">使用区域</span><span class="sxs-lookup"><span data-stu-id="e927c-116">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
