---
title: "如何：在形状中平铺图像"
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
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d8726322e9443042b76c28e7b4b22ebc51c871bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="83511-102">如何：在形状中平铺图像</span><span class="sxs-lookup"><span data-stu-id="83511-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="83511-103">就像磁贴可以彼此以覆盖层相邻放置，可以将矩形映像彼此相邻放置于填充 （磁贴） 形状。</span><span class="sxs-lookup"><span data-stu-id="83511-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="83511-104">若要磁贴形状的内部，使用纹理画笔。</span><span class="sxs-lookup"><span data-stu-id="83511-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="83511-105">构造时<xref:System.Drawing.TextureBrush>对象，将传递给构造函数的自变量之一为<xref:System.Drawing.Image>对象。</span><span class="sxs-lookup"><span data-stu-id="83511-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="83511-106">当你使用的纹理画笔绘制形状的内部时，形状填充使用此映像的重复副本。</span><span class="sxs-lookup"><span data-stu-id="83511-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="83511-107">包装模式属性<xref:System.Drawing.TextureBrush>对象确定如何映像是面向随着矩形网格中重复。</span><span class="sxs-lookup"><span data-stu-id="83511-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="83511-108">您可以进行所有磁贴在网格中的具有相同的方向，也可以从一个网格位置到下一个翻转的图像。</span><span class="sxs-lookup"><span data-stu-id="83511-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="83511-109">翻转可以水平、 垂直或两者。</span><span class="sxs-lookup"><span data-stu-id="83511-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="83511-110">下面的示例演示使用不同类型的翻转平铺。</span><span class="sxs-lookup"><span data-stu-id="83511-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="83511-111">平铺图像</span><span class="sxs-lookup"><span data-stu-id="83511-111">To tile an image</span></span>  
  
-   <span data-ttu-id="83511-112">此示例使用以下 75 × 75 图像平铺 200 × 200 的矩形。</span><span class="sxs-lookup"><span data-stu-id="83511-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="83511-113">![磁贴 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="83511-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="83511-114">下图显示如何在该矩形平铺与映像。</span><span class="sxs-lookup"><span data-stu-id="83511-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="83511-115">请注意，所有图块具有相同的方向;没有翻转。</span><span class="sxs-lookup"><span data-stu-id="83511-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="83511-116">![磁贴 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="83511-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="83511-117">若要水平时平铺翻转图像</span><span class="sxs-lookup"><span data-stu-id="83511-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="83511-118">此示例使用相同的 75 × 75 图像以填充 200 × 200 矩形。</span><span class="sxs-lookup"><span data-stu-id="83511-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="83511-119">设置环绕模式为水平翻转图像。</span><span class="sxs-lookup"><span data-stu-id="83511-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="83511-120">下图显示如何在该矩形平铺与映像。</span><span class="sxs-lookup"><span data-stu-id="83511-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="83511-121">请注意当你从一个磁贴移动到给定行中下一步，水平翻转图像。</span><span class="sxs-lookup"><span data-stu-id="83511-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="83511-122">![磁贴 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="83511-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="83511-123">若要垂直时平铺翻转图像</span><span class="sxs-lookup"><span data-stu-id="83511-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="83511-124">此示例使用相同的 75 × 75 图像以填充 200 × 200 矩形。</span><span class="sxs-lookup"><span data-stu-id="83511-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="83511-125">设置环绕模式为垂直翻转图像。</span><span class="sxs-lookup"><span data-stu-id="83511-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="83511-126">平铺时水平和垂直翻转图像</span><span class="sxs-lookup"><span data-stu-id="83511-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="83511-127">此示例使用相同的 75 × 75 图像平铺 200 × 200 的矩形。</span><span class="sxs-lookup"><span data-stu-id="83511-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="83511-128">设置环绕模式为水平和垂直翻转图像。</span><span class="sxs-lookup"><span data-stu-id="83511-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="83511-129">下图显示如何在该矩形平铺的映像。</span><span class="sxs-lookup"><span data-stu-id="83511-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="83511-130">请注意，当您从一个磁贴移动到给定行中下一步，水平翻转图像，则但当你从一个磁贴移动到给定列中下一步，垂直翻转图像。</span><span class="sxs-lookup"><span data-stu-id="83511-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="83511-131">![磁贴 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="83511-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="83511-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="83511-132">See Also</span></span>  
 [<span data-ttu-id="83511-133">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="83511-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
