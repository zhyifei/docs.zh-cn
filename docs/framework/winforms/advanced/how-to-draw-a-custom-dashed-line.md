---
title: 如何：绘制自定义虚线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 39dde3bb45165783171326b79e98744807350952
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521610"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="450ee-102">如何：绘制自定义虚线</span><span class="sxs-lookup"><span data-stu-id="450ee-102">How to: Draw a Custom Dashed Line</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="450ee-103"> 提供几种中列出的短划线样式<xref:System.Drawing.Drawing2D.DashStyle>枚举。</span><span class="sxs-lookup"><span data-stu-id="450ee-103"> provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="450ee-104">如果这些标准的短划线样式无法满足你的需求，你可以创建自定义的短划线图案。</span><span class="sxs-lookup"><span data-stu-id="450ee-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="450ee-105">示例</span><span class="sxs-lookup"><span data-stu-id="450ee-105">Example</span></span>  
 <span data-ttu-id="450ee-106">若要绘制自定义虚线，放置在数组中的短划线和空白的长度，并将该数组指定为的值<xref:System.Drawing.Pen.DashPattern%2A>属性<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="450ee-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="450ee-107">下面的示例绘制自定义虚线基于阵列上`{5, 2, 15, 4}`。</span><span class="sxs-lookup"><span data-stu-id="450ee-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="450ee-108">如果数组的元素乘以钢笔的宽度为 5，则获取`{25, 10, 75, 20}`。</span><span class="sxs-lookup"><span data-stu-id="450ee-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="450ee-109">显示的短划线备用在 25 和 75，之间的长度和空间交替效果的长度介于 10 和 20 之间。</span><span class="sxs-lookup"><span data-stu-id="450ee-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="450ee-110">下图显示生成的虚线。</span><span class="sxs-lookup"><span data-stu-id="450ee-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="450ee-111">请注意，最终的短划线必须是少于 25 个单元，以便可以在结束行 （405，5）。</span><span class="sxs-lookup"><span data-stu-id="450ee-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="450ee-112">![钢笔](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="450ee-112">![Pens](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="450ee-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="450ee-113">Compiling the Code</span></span>  
 <span data-ttu-id="450ee-114">创建 Windows 窗体和处理该窗体<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="450ee-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="450ee-115">前面将代码粘贴到<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="450ee-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="450ee-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="450ee-116">See Also</span></span>  
 [<span data-ttu-id="450ee-117">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="450ee-117">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
