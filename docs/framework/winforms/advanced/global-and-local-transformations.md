---
title: "全局转换和局部转换"
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
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e8d05bd0c3e76d643d56b652c8849eef1045ea8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="global-and-local-transformations"></a><span data-ttu-id="86fa2-102">全局转换和局部转换</span><span class="sxs-lookup"><span data-stu-id="86fa2-102">Global and Local Transformations</span></span>
<span data-ttu-id="86fa2-103">全局转换是一个转换，它适用于通过绘制每一项给定<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="86fa2-103">A global transformation is a transformation that applies to every item drawn by a given <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="86fa2-104">与此相反，本地转换是适用于特定项要绘制一个转换。</span><span class="sxs-lookup"><span data-stu-id="86fa2-104">In contrast, a local transformation is a transformation that applies to a specific item to be drawn.</span></span>  
  
## <a name="global-transformations"></a><span data-ttu-id="86fa2-105">全局转换</span><span class="sxs-lookup"><span data-stu-id="86fa2-105">Global Transformations</span></span>  
 <span data-ttu-id="86fa2-106">若要创建的全局转换，构造<xref:System.Drawing.Graphics>对象，以及然后操作其<xref:System.Drawing.Graphics.Transform%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="86fa2-106">To create a global transformation, construct a <xref:System.Drawing.Graphics> object, and then manipulate its <xref:System.Drawing.Graphics.Transform%2A> property.</span></span> <span data-ttu-id="86fa2-107"><xref:System.Drawing.Graphics.Transform%2A>属性是<xref:System.Drawing.Drawing2D.Matrix>对象，因此它可以存放仿射转换的任何序列。</span><span class="sxs-lookup"><span data-stu-id="86fa2-107">The <xref:System.Drawing.Graphics.Transform%2A> property is a <xref:System.Drawing.Drawing2D.Matrix> object, so it can hold any sequence of affine transformations.</span></span> <span data-ttu-id="86fa2-108">转换存储在<xref:System.Drawing.Graphics.Transform%2A>称为世界转换的属性。</span><span class="sxs-lookup"><span data-stu-id="86fa2-108">The transformation stored in the <xref:System.Drawing.Graphics.Transform%2A> property is called the world transformation.</span></span> <span data-ttu-id="86fa2-109"><xref:System.Drawing.Graphics>类提供了构建复合世界转换的几种方法： <xref:System.Drawing.Graphics.MultiplyTransform%2A>， <xref:System.Drawing.Graphics.RotateTransform%2A>， <xref:System.Drawing.Graphics.ScaleTransform%2A>，和<xref:System.Drawing.Graphics.TranslateTransform%2A>。</span><span class="sxs-lookup"><span data-stu-id="86fa2-109">The <xref:System.Drawing.Graphics> class provides several methods for building up a composite world transformation: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, and <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span></span> <span data-ttu-id="86fa2-110">下面的示例绘制一个椭圆两次： 一次之前创建的世界变换和之后的一次。</span><span class="sxs-lookup"><span data-stu-id="86fa2-110">The following example draws an ellipse twice: once before creating a world transformation and once after.</span></span> <span data-ttu-id="86fa2-111">转换第一次在 y 方向，0.5 的按比例调整然后平移在 x 方向的 50 个单位并且然后将旋转 30 度。</span><span class="sxs-lookup"><span data-stu-id="86fa2-111">The transformation first scales by a factor of 0.5 in the y direction, then translates 50 units in the x direction, and then rotates 30 degrees.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 <span data-ttu-id="86fa2-112">下图显示了所涉及的转换矩阵。</span><span class="sxs-lookup"><span data-stu-id="86fa2-112">The following illustration shows the matrices involved in the transformation.</span></span>  
  
 <span data-ttu-id="86fa2-113">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")</span><span class="sxs-lookup"><span data-stu-id="86fa2-113">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86fa2-114">在前面的示例中，坐标系统，这是客户端区域的左上角原点顺转动椭圆。</span><span class="sxs-lookup"><span data-stu-id="86fa2-114">In the preceding example, the ellipse is rotated about the origin of the coordinate system, which is at the upper-left corner of the client area.</span></span> <span data-ttu-id="86fa2-115">这将生成不同的结果比轮换围绕其自身中心椭圆。</span><span class="sxs-lookup"><span data-stu-id="86fa2-115">This produces a different result than rotating the ellipse about its own center.</span></span>  
  
## <a name="local-transformations"></a><span data-ttu-id="86fa2-116">局部变换</span><span class="sxs-lookup"><span data-stu-id="86fa2-116">Local Transformations</span></span>  
 <span data-ttu-id="86fa2-117">本地转换适用于要绘制的特定项。</span><span class="sxs-lookup"><span data-stu-id="86fa2-117">A local transformation applies to a specific item to be drawn.</span></span> <span data-ttu-id="86fa2-118">例如，<xref:System.Drawing.Drawing2D.GraphicsPath>对象具有<xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A>，可以将转换该路径的数据点的方法。</span><span class="sxs-lookup"><span data-stu-id="86fa2-118">For example, a <xref:System.Drawing.Drawing2D.GraphicsPath> object has a <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> method that allows you to transform the data points of that path.</span></span> <span data-ttu-id="86fa2-119">下面的示例绘制一个具有任何转换的矩形和具有旋转转换的路径。</span><span class="sxs-lookup"><span data-stu-id="86fa2-119">The following example draws a rectangle with no transformation and a path with a rotation transformation.</span></span> <span data-ttu-id="86fa2-120">（假定没有任何世界转换。）</span><span class="sxs-lookup"><span data-stu-id="86fa2-120">(Assume that there is no world transformation.)</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 <span data-ttu-id="86fa2-121">你可以组合与局部变换以实现各种结果的世界转换。</span><span class="sxs-lookup"><span data-stu-id="86fa2-121">You can combine the world transformation with local transformations to achieve a variety of results.</span></span> <span data-ttu-id="86fa2-122">例如，可以使用世界转换修改坐标系统，并使用局部变换旋转和缩放绘制在新的坐标系统上的对象。</span><span class="sxs-lookup"><span data-stu-id="86fa2-122">For example, you can use the world transformation to revise the coordinate system and use local transformations to rotate and scale objects drawn on the new coordinate system.</span></span>  
  
 <span data-ttu-id="86fa2-123">假设您希望一个坐标系统中已从工作区左边缘的原点 200 像素以及从客户端区域的顶部 150 像素。</span><span class="sxs-lookup"><span data-stu-id="86fa2-123">Suppose you want a coordinate system that has its origin 200 pixels from the left edge of the client area and 150 pixels from the top of the client area.</span></span> <span data-ttu-id="86fa2-124">此外，假设你想要像素，且 x 轴指向右侧和朝上 y 轴的度量单位。</span><span class="sxs-lookup"><span data-stu-id="86fa2-124">Furthermore, assume that you want the unit of measure to be the pixel, with the x-axis pointing to the right and the y-axis pointing up.</span></span> <span data-ttu-id="86fa2-125">默认坐标系统有指向下，y 轴，因此你需要在水平轴执行反射。</span><span class="sxs-lookup"><span data-stu-id="86fa2-125">The default coordinate system has the y-axis pointing down, so you need to perform a reflection across the horizontal axis.</span></span> <span data-ttu-id="86fa2-126">下图显示此类反射的矩阵。</span><span class="sxs-lookup"><span data-stu-id="86fa2-126">The following illustration shows the matrix of such a reflection.</span></span>  
  
 <span data-ttu-id="86fa2-127">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")</span><span class="sxs-lookup"><span data-stu-id="86fa2-127">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")</span></span>  
  
 <span data-ttu-id="86fa2-128">接下来，假定你需要执行转换 200 个单位的向右和向下的 150 个单位。</span><span class="sxs-lookup"><span data-stu-id="86fa2-128">Next, assume you need to perform a translation 200 units to the right and 150 units down.</span></span>  
  
 <span data-ttu-id="86fa2-129">下面的示例建立刚刚介绍的设置的世界变换的坐标系<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="86fa2-129">The following example establishes the coordinate system just described by setting the world transformation of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 <span data-ttu-id="86fa2-130">下面的代码 （在前面的示例中的末尾放置） 创建包含单个矩形与新的坐标系统的原点在其左下角的路径。</span><span class="sxs-lookup"><span data-stu-id="86fa2-130">The following code (placed at the end of the preceding example) creates a path that consists of a single rectangle with its lower-left corner at the origin of the new coordinate system.</span></span> <span data-ttu-id="86fa2-131">一次不使用局部变换和局部变换，将一次填充的矩形。</span><span class="sxs-lookup"><span data-stu-id="86fa2-131">The rectangle is filled once with no local transformation and once with a local transformation.</span></span> <span data-ttu-id="86fa2-132">按 2 的 30 度旋转后跟的系数水平缩放包含的局部变换。</span><span class="sxs-lookup"><span data-stu-id="86fa2-132">The local transformation consists of a horizontal scaling by a factor of 2 followed by a 30-degree rotation.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 <span data-ttu-id="86fa2-133">下图显示新的坐标系统和两个矩形。</span><span class="sxs-lookup"><span data-stu-id="86fa2-133">The following illustration shows the new coordinate system and the two rectangles.</span></span>  
  
 <span data-ttu-id="86fa2-134">![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")</span><span class="sxs-lookup"><span data-stu-id="86fa2-134">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86fa2-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="86fa2-135">See Also</span></span>  
 [<span data-ttu-id="86fa2-136">坐标系统和转换</span><span class="sxs-lookup"><span data-stu-id="86fa2-136">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="86fa2-137">在托管 GDI+ 中使用转换</span><span class="sxs-lookup"><span data-stu-id="86fa2-137">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
