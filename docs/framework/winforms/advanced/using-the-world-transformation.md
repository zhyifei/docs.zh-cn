---
title: "使用世界转换"
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
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8599f2e154e05fd2d43b094041989c4a3a5dbc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="76bd1-102">使用世界转换</span><span class="sxs-lookup"><span data-stu-id="76bd1-102">Using the World Transformation</span></span>
<span data-ttu-id="76bd1-103">世界转换是的一个属性<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="76bd1-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="76bd1-104">指定的世界转换的数字以存储<xref:System.Drawing.Drawing2D.Matrix>对象，用于表示 3 × 3 矩阵。</span><span class="sxs-lookup"><span data-stu-id="76bd1-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="76bd1-105"><xref:System.Drawing.Drawing2D.Matrix>和<xref:System.Drawing.Graphics>类可以用多种方法用于设置数字的世界变换矩阵。</span><span class="sxs-lookup"><span data-stu-id="76bd1-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="76bd1-106">不同类型的转换</span><span class="sxs-lookup"><span data-stu-id="76bd1-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="76bd1-107">在下面的示例中，代码将首先创建 50 × 50 矩形并将其定位在原点 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="76bd1-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="76bd1-108">原点位于客户端区域的左上角。</span><span class="sxs-lookup"><span data-stu-id="76bd1-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="76bd1-109">下面的代码应用通过 1.75 英寸 x 方向的因素，扩展矩形，并将该矩形收缩的 y 方向的 0.5 倍的缩放转换：</span><span class="sxs-lookup"><span data-stu-id="76bd1-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="76bd1-110">结果是一个矩形，即在 x 方向较长和短于原始 y 方向。</span><span class="sxs-lookup"><span data-stu-id="76bd1-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="76bd1-111">要旋转而不是扩展的矩形，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="76bd1-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="76bd1-112">若要翻译矩形，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="76bd1-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="76bd1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="76bd1-113">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [<span data-ttu-id="76bd1-114">坐标系统和转换</span><span class="sxs-lookup"><span data-stu-id="76bd1-114">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="76bd1-115">在托管 GDI+ 中使用转换</span><span class="sxs-lookup"><span data-stu-id="76bd1-115">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
