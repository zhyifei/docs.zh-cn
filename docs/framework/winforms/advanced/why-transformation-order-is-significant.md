---
title: "为什么转换顺序非常重要"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order signficance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd3363a1afb8658ed3bb27359259cb752464507d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="why-transformation-order-is-significant"></a><span data-ttu-id="44c38-102">为什么转换顺序非常重要</span><span class="sxs-lookup"><span data-stu-id="44c38-102">Why Transformation Order Is Significant</span></span>
<span data-ttu-id="44c38-103">单个<xref:System.Drawing.Drawing2D.Matrix>对象可以存储一次转换的序列。</span><span class="sxs-lookup"><span data-stu-id="44c38-103">A single <xref:System.Drawing.Drawing2D.Matrix> object can store a single transformation or a sequence of transformations.</span></span> <span data-ttu-id="44c38-104">后者称为复合转换。</span><span class="sxs-lookup"><span data-stu-id="44c38-104">The latter is called a composite transformation.</span></span> <span data-ttu-id="44c38-105">复合转换的矩阵被获取的各个变换的矩阵相乘。</span><span class="sxs-lookup"><span data-stu-id="44c38-105">The matrix of a composite transformation is obtained by multiplying the matrices of individual transformations.</span></span>  
  
## <a name="composite-transform-examples"></a><span data-ttu-id="44c38-106">复合转换示例</span><span class="sxs-lookup"><span data-stu-id="44c38-106">Composite Transform Examples</span></span>  
 <span data-ttu-id="44c38-107">在复合转换中，各个变换之间的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="44c38-107">In a composite transformation, the order of individual transformations is important.</span></span> <span data-ttu-id="44c38-108">例如，如果第一次旋转，则缩放，则转换，你获得不同的结果不是如果首先将转换，然后旋转，则缩放。</span><span class="sxs-lookup"><span data-stu-id="44c38-108">For example, if you first rotate, then scale, then translate, you get a different result than if you first translate, then rotate, then scale.</span></span> <span data-ttu-id="44c38-109">在[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，复合转换生成从左到右。</span><span class="sxs-lookup"><span data-stu-id="44c38-109">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], composite transformations are built from left to right.</span></span> <span data-ttu-id="44c38-110">如果 S、 R 和 T 分别缩放、 旋转和平移矩阵，然后产品 （按此顺序） 的 SRT 是该第一个刻度的复合变换的矩阵，旋转，然后将转换。</span><span class="sxs-lookup"><span data-stu-id="44c38-110">If S, R, and T are scale, rotation, and translation matrices respectively, then the product SRT (in that order) is the matrix of the composite transformation that first scales, then rotates, then translates.</span></span> <span data-ttu-id="44c38-111">生成产品的矩阵 SRT 是不同的生成的乘积 TRS 的矩阵。</span><span class="sxs-lookup"><span data-stu-id="44c38-111">The matrix produced by the product SRT is different from the matrix produced by the product TRS.</span></span>  
  
 <span data-ttu-id="44c38-112">顺序很重要的原因之一是，这样像旋转和缩放转换是针对坐标系统的原点。</span><span class="sxs-lookup"><span data-stu-id="44c38-112">One reason order is significant is that transformations like rotation and scaling are done with respect to the origin of the coordinate system.</span></span> <span data-ttu-id="44c38-113">缩放以原点中心的对象生成比缩放已离开源的对象不同的结果。</span><span class="sxs-lookup"><span data-stu-id="44c38-113">Scaling an object that is centered at the origin produces a different result than scaling an object that has been moved away from the origin.</span></span> <span data-ttu-id="44c38-114">同样，轮换基于原点居中的对象生成已离开源的对象与旋转不同的结果。</span><span class="sxs-lookup"><span data-stu-id="44c38-114">Similarly, rotating an object that is centered at the origin produces a different result than rotating an object that has been moved away from the origin.</span></span>  
  
 <span data-ttu-id="44c38-115">下面的示例结合缩放、 旋转和平移 （按照这个顺序），以形成复合转换。</span><span class="sxs-lookup"><span data-stu-id="44c38-115">The following example combines scaling, rotation and translation (in that order) to form a composite transformation.</span></span> <span data-ttu-id="44c38-116">自变量<xref:System.Drawing.Drawing2D.MatrixOrder.Append>传递给<xref:System.Drawing.Graphics.RotateTransform%2A>方法指示旋转将遵循这样的缩放。</span><span class="sxs-lookup"><span data-stu-id="44c38-116">The argument <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passed to the <xref:System.Drawing.Graphics.RotateTransform%2A> method indicates that the rotation will follow the scaling.</span></span> <span data-ttu-id="44c38-117">同样，参数<xref:System.Drawing.Drawing2D.MatrixOrder.Append>传递给<xref:System.Drawing.Graphics.TranslateTransform%2A>方法指示转换将遵循旋转。</span><span class="sxs-lookup"><span data-stu-id="44c38-117">Likewise, the argument <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passed to the <xref:System.Drawing.Graphics.TranslateTransform%2A> method indicates that the translation will follow the rotation.</span></span> <span data-ttu-id="44c38-118"><xref:System.Drawing.Drawing2D.MatrixOrder.Append>和<xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>成员的<xref:System.Drawing.Drawing2D.MatrixOrder>枚举。</span><span class="sxs-lookup"><span data-stu-id="44c38-118"><xref:System.Drawing.Drawing2D.MatrixOrder.Append> and <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> are members of the <xref:System.Drawing.Drawing2D.MatrixOrder> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 <span data-ttu-id="44c38-119">下面的示例使相同的方法调用与上面的示例中，但在调用的顺序相反。</span><span class="sxs-lookup"><span data-stu-id="44c38-119">The following example makes the same method calls as the preceding example, but the order of the calls is reversed.</span></span> <span data-ttu-id="44c38-120">生成的运算顺序平移、 依次旋转和缩放，这样会生成非常不同的结果比第一个刻度，然后旋转，转换。</span><span class="sxs-lookup"><span data-stu-id="44c38-120">The resulting order of operations is first translate, then rotate, then scale, which produces a very different result than first scale, then rotate, then translate.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 <span data-ttu-id="44c38-121">若要反转的复合转换中的各个转换顺序的一种方法是要反转的一系列方法调用的顺序。</span><span class="sxs-lookup"><span data-stu-id="44c38-121">One way to reverse the order of individual transformations in a composite transformation is to reverse the order of a sequence of method calls.</span></span> <span data-ttu-id="44c38-122">第二种方法控制的运算顺序是更改矩阵顺序的参数。</span><span class="sxs-lookup"><span data-stu-id="44c38-122">A second way to control the order of operations is to change the matrix order argument.</span></span> <span data-ttu-id="44c38-123">下面的示例是前面示例中，但相同<xref:System.Drawing.Drawing2D.MatrixOrder.Append>已更改为<xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>。</span><span class="sxs-lookup"><span data-stu-id="44c38-123">The following example is the same as the preceding example, except that <xref:System.Drawing.Drawing2D.MatrixOrder.Append> has been changed to <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>.</span></span> <span data-ttu-id="44c38-124">矩阵乘法的顺序排序，其中 S、 R、 T 会缩放、 旋转的矩阵和翻译，分别。</span><span class="sxs-lookup"><span data-stu-id="44c38-124">The matrix multiplication is done in the order SRT, where S, R, and T are the matrices for scale, rotate, and translate, respectively.</span></span> <span data-ttu-id="44c38-125">复合转换的顺序第一个刻度，然后旋转，则转换。</span><span class="sxs-lookup"><span data-stu-id="44c38-125">The order of the composite transformation is first scale, then rotate, then translate.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 <span data-ttu-id="44c38-126">立即上述示例的结果作为本主题中的第一个示例的结果是相同的。</span><span class="sxs-lookup"><span data-stu-id="44c38-126">The result of the immediately preceding example is the same as the result of the first example in this topic.</span></span> <span data-ttu-id="44c38-127">这是因为我们反转方法调用的顺序和矩阵乘法的顺序。</span><span class="sxs-lookup"><span data-stu-id="44c38-127">This is because we reversed both the order of the method calls and the order of the matrix multiplication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c38-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="44c38-128">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [<span data-ttu-id="44c38-129">坐标系统和转换</span><span class="sxs-lookup"><span data-stu-id="44c38-129">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="44c38-130">在托管 GDI+ 中使用转换</span><span class="sxs-lookup"><span data-stu-id="44c38-130">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
