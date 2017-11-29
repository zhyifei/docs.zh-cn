---
title: "Windows 窗体坐标"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ecb47efdd69730350cf98e1c7b1e49150ad324d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="9cded-102">Windows 窗体坐标</span><span class="sxs-lookup"><span data-stu-id="9cded-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="9cded-103">Windows 窗体坐标系统基于设备坐标，并度量值时在 Windows 窗体中绘制的基本单位是设备单元 （通常情况下，像素）。</span><span class="sxs-lookup"><span data-stu-id="9cded-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="9cded-104">在屏幕上的点的 x 坐标和 y 坐标对所述增加到右侧和 y 坐标增加从顶部到底部的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="9cded-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="9cded-105">来源，相对于屏幕中，位置将有所不同具体取决于是否指定屏幕或客户端坐标。</span><span class="sxs-lookup"><span data-stu-id="9cded-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="9cded-106">屏幕坐标</span><span class="sxs-lookup"><span data-stu-id="9cded-106">Screen Coordinates</span></span>  
 <span data-ttu-id="9cded-107">Windows 窗体应用程序指定屏幕坐标中的屏幕上窗口的位置。</span><span class="sxs-lookup"><span data-stu-id="9cded-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="9cded-108">屏幕坐标的来源是屏幕的左上角。</span><span class="sxs-lookup"><span data-stu-id="9cded-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="9cded-109">窗口的完整位置通常由<xref:System.Drawing.Rectangle>结构，它包含两个定义窗口的左上角和右下角的点的屏幕坐标。</span><span class="sxs-lookup"><span data-stu-id="9cded-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="9cded-110">客户端坐标</span><span class="sxs-lookup"><span data-stu-id="9cded-110">Client Coordinates</span></span>  
 <span data-ttu-id="9cded-111">Windows 窗体应用程序窗体或控件使用客户端坐标中指定的点的位置。</span><span class="sxs-lookup"><span data-stu-id="9cded-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="9cded-112">工作区坐标中的源是控件或窗体的工作区的左上角。</span><span class="sxs-lookup"><span data-stu-id="9cded-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="9cded-113">客户端坐标可确保在应用程序可以在窗体或控件，无论窗体或屏幕上的控件的位置中绘制时使用一致的坐标值。</span><span class="sxs-lookup"><span data-stu-id="9cded-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="9cded-114">客户端区域的尺寸，还介绍了由<xref:System.Drawing.Rectangle>结构，其中包含工作区坐标中的区。</span><span class="sxs-lookup"><span data-stu-id="9cded-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="9cded-115">在所有情况下，矩形的左上角的坐标包含在客户端区域中，，而不对此右下角坐标。</span><span class="sxs-lookup"><span data-stu-id="9cded-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="9cded-116">图形操作不包括的客户端区域的上边缘右和下边缘。</span><span class="sxs-lookup"><span data-stu-id="9cded-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="9cded-117">例如<xref:System.Drawing.Graphics.FillRectangle%2A>方法将一直填充到指定的矩形的上边缘右和下边缘，但不是会包括这些边缘。</span><span class="sxs-lookup"><span data-stu-id="9cded-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="9cded-118">将映射到另一种类型的坐标从</span><span class="sxs-lookup"><span data-stu-id="9cded-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="9cded-119">有时，你可能需要从屏幕坐标映射到客户端坐标。</span><span class="sxs-lookup"><span data-stu-id="9cded-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="9cded-120">你可以轻松地实现此目的使用<xref:System.Windows.Forms.Control.PointToClient%2A>和<xref:System.Windows.Forms.Control.PointToScreen%2A>方法中提供<xref:System.Windows.Forms.Control>类。</span><span class="sxs-lookup"><span data-stu-id="9cded-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="9cded-121">例如，<xref:System.Windows.Forms.Control.MousePosition%2A>属性<xref:System.Windows.Forms.Control>报告在屏幕坐标中，但你可能想要将它们转换成工作区坐标。</span><span class="sxs-lookup"><span data-stu-id="9cded-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cded-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cded-122">See Also</span></span>  
 <xref:System.Windows.Forms.Control.PointToClient%2A>  
 <xref:System.Windows.Forms.Control.PointToScreen%2A>
