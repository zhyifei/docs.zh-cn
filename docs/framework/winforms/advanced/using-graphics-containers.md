---
title: 使用图形容器
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766150"
---
# <a name="using-graphics-containers"></a><span data-ttu-id="c7db1-102">使用图形容器</span><span class="sxs-lookup"><span data-stu-id="c7db1-102">Using Graphics Containers</span></span>
<span data-ttu-id="c7db1-103">一个<xref:System.Drawing.Graphics>对象提供的方法，如<xref:System.Drawing.Graphics.DrawLine%2A>， <xref:System.Drawing.Graphics.DrawImage%2A>，和<xref:System.Drawing.Graphics.DrawString%2A>用于显示矢量图像、 光栅图像和文本。</span><span class="sxs-lookup"><span data-stu-id="c7db1-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="c7db1-104">一个<xref:System.Drawing.Graphics>对象还具有影响的质量和方向绘制的项的多个属性。</span><span class="sxs-lookup"><span data-stu-id="c7db1-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="c7db1-105">例如，平滑的模式属性确定是否抗锯齿应用于直线和曲线和世界变换属性影响的位置和旋转绘制的项。</span><span class="sxs-lookup"><span data-stu-id="c7db1-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="c7db1-106">一个<xref:System.Drawing.Graphics>对象是与特定显示设备相关联。</span><span class="sxs-lookup"><span data-stu-id="c7db1-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="c7db1-107">当你使用<xref:System.Drawing.Graphics>对象中要在窗口中，绘制<xref:System.Drawing.Graphics>对象也是与该特定窗口相关联。</span><span class="sxs-lookup"><span data-stu-id="c7db1-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="c7db1-108">一个<xref:System.Drawing.Graphics>对象可以被认为是作为容器因为它包含一组影响绘图的属性和链接到特定于设备的信息。</span><span class="sxs-lookup"><span data-stu-id="c7db1-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="c7db1-109">可以创建第二个容器中的现有<xref:System.Drawing.Graphics>对象通过调用<xref:System.Drawing.Graphics.BeginContainer%2A>方法的<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="c7db1-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7db1-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="c7db1-110">In This Section</span></span>  
 [<span data-ttu-id="c7db1-111">管理图形对象的状态</span><span class="sxs-lookup"><span data-stu-id="c7db1-111">Managing the State of a Graphics Object</span></span>](managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="c7db1-112">介绍如何管理质量设置、 剪辑区域和转换的<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="c7db1-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="c7db1-113">使用嵌套的图形容器</span><span class="sxs-lookup"><span data-stu-id="c7db1-113">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)  
 <span data-ttu-id="c7db1-114">演示如何使用容器来控制的状态<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="c7db1-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
