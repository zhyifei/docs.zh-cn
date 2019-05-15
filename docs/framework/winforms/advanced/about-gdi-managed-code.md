---
title: 关于 GDI+ 托管代码
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, about GDI+
- GDI+
- graphics [Windows Forms], GDI+
ms.assetid: a98a76ab-e455-49c9-891c-0491ac932f2c
ms.openlocfilehash: 4c7632933e29a59c1db46f84360e271f27edf8b8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588615"
---
# <a name="about-gdi-managed-code"></a><span data-ttu-id="291ad-102">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="291ad-102">About GDI+ Managed Code</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="291ad-103">是 Windows 操作系统提供二维矢量图形、图像处理和版式的部分。</span><span class="sxs-lookup"><span data-stu-id="291ad-103">is the portion of the Windows operating system that provides two-dimensional vector graphics, imaging, and typography.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="291ad-104">在 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]（早期的 Windows 版本包含的图形设备接口）的基础上进行了改进，添加了新功能和优化了现有功能。</span><span class="sxs-lookup"><span data-stu-id="291ad-104">improves on [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (the Graphics Device Interface included with earlier versions of Windows) by adding new features and by optimizing existing features.</span></span>  
  
 <span data-ttu-id="291ad-105">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]托管的类接口 （一组包装） 是.NET Framework，用于构建、 部署和运行 XML Web 服务和其他应用程序的环境的一部分。</span><span class="sxs-lookup"><span data-stu-id="291ad-105">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] managed class interface (a set of wrappers) is part of the .NET Framework, an environment for building, deploying, and running XML Web services and other applications.</span></span>  
  
 <span data-ttu-id="291ad-106">本节为使用托管代码的程序员提供有关 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API 的信息。</span><span class="sxs-lookup"><span data-stu-id="291ad-106">This section provides information about the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API for programmers using managed code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="291ad-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="291ad-107">In This Section</span></span>  
 [<span data-ttu-id="291ad-108">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="291ad-108">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)  
 <span data-ttu-id="291ad-109">讨论矢量图形。</span><span class="sxs-lookup"><span data-stu-id="291ad-109">Discusses vector graphics.</span></span>  
  
 [<span data-ttu-id="291ad-110">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="291ad-110">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="291ad-111">讨论可用的图像类型以及如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="291ad-111">Discusses the type of images available and how to work with them.</span></span>  
  
 [<span data-ttu-id="291ad-112">坐标系统和转换</span><span class="sxs-lookup"><span data-stu-id="291ad-112">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)  
 <span data-ttu-id="291ad-113">讨论如何使用 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 转换图形。</span><span class="sxs-lookup"><span data-stu-id="291ad-113">Discusses how to transform graphics with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="291ad-114">参考</span><span class="sxs-lookup"><span data-stu-id="291ad-114">Reference</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <span data-ttu-id="291ad-115">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="291ad-115">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Drawing.Image?displayProperty=nameWithType>  
 <span data-ttu-id="291ad-116">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="291ad-116">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="291ad-117"><xref:System.Drawing.Bitmap?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="291ad-117"><xref:System.Drawing.Bitmap?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="291ad-118">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="291ad-118">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="291ad-119"><xref:System.Drawing.Imaging.Metafile?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="291ad-119"><xref:System.Drawing.Imaging.Metafile?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="291ad-120">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="291ad-120">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="291ad-121"><xref:System.Drawing.Font?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="291ad-121"><xref:System.Drawing.Font?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="291ad-122">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="291ad-122">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="291ad-123"><xref:System.Drawing.Brush?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="291ad-123"><xref:System.Drawing.Brush?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="291ad-124">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="291ad-124">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="291ad-125"><xref:System.Drawing.Color?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="291ad-125"><xref:System.Drawing.Color?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="291ad-126">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="291ad-126">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.Matrix?displayProperty=nameWithType>  
 <span data-ttu-id="291ad-127">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="291ad-127">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType>  
 <span data-ttu-id="291ad-128">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="291ad-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="291ad-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="291ad-129">Related Sections</span></span>  
 <span data-ttu-id="291ad-130">[使用托管的图形类](using-managed-graphics-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="291ad-130">[Using Managed Graphics Classes](using-managed-graphics-classes.md).</span></span>  
 <span data-ttu-id="291ad-131">包含链接，该链接指向演示如何使用 `Graphics` 编程接口的主题。</span><span class="sxs-lookup"><span data-stu-id="291ad-131">Contains links to topics that demonstrate how to use the `Graphics` programming interface.</span></span>
