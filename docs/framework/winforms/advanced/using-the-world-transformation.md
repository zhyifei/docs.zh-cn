---
title: 使用世界变换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139953"
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="f15a1-102">使用世界变换</span><span class="sxs-lookup"><span data-stu-id="f15a1-102">Using the World Transformation</span></span>
<span data-ttu-id="f15a1-103">世界转换是一个属性的<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="f15a1-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="f15a1-104">指定世界转换的数字存储在<xref:System.Drawing.Drawing2D.Matrix>对象，表示 3 × 3 矩阵。</span><span class="sxs-lookup"><span data-stu-id="f15a1-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="f15a1-105"><xref:System.Drawing.Drawing2D.Matrix>和<xref:System.Drawing.Graphics>类有多种方法来设置世界转换矩阵中的数字。</span><span class="sxs-lookup"><span data-stu-id="f15a1-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="f15a1-106">不同类型的转换</span><span class="sxs-lookup"><span data-stu-id="f15a1-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="f15a1-107">在以下示例中，代码首先创建 50 × 50 矩形并将其定位在原点 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="f15a1-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="f15a1-108">原点位于工作区的左上角。</span><span class="sxs-lookup"><span data-stu-id="f15a1-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="f15a1-109">下面的代码应用的缩放转换，可通过沿 x 方向的 1.75 扩展矩形并通过在 y 方向的 0.5 的比例缩小矩形：</span><span class="sxs-lookup"><span data-stu-id="f15a1-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="f15a1-110">结果是沿 x 方向的时间更长且 y 方向的长度小于原始矩形。</span><span class="sxs-lookup"><span data-stu-id="f15a1-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="f15a1-111">若要旋转而不是其缩放矩形，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="f15a1-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="f15a1-112">若要转换的矩形，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="f15a1-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="f15a1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f15a1-113">See also</span></span>

- <xref:System.Drawing.Drawing2D.Matrix>
- [<span data-ttu-id="f15a1-114">坐标系统和转换</span><span class="sxs-lookup"><span data-stu-id="f15a1-114">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="f15a1-115">在托管 GDI+ 中使用转换</span><span class="sxs-lookup"><span data-stu-id="f15a1-115">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
