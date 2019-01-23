---
title: Windows 窗体坐标
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: a6f082eb57a9cfe1af0d4207cbf5226637191c90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556046"
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="bbf14-102">Windows 窗体坐标</span><span class="sxs-lookup"><span data-stu-id="bbf14-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="bbf14-103">Windows 窗体坐标系统取决于设备坐标，并在 Windows 窗体中绘制时的度量值的基本单位是将设备单位 （通常情况下，像素）。</span><span class="sxs-lookup"><span data-stu-id="bbf14-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="bbf14-104">在屏幕上的点的 x 坐标和 y 坐标对所述增加到右侧和 y 坐标增加从上到下的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="bbf14-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="bbf14-105">原点，相对于屏幕的位置不定，具体取决于是否要指定屏幕或客户端坐标。</span><span class="sxs-lookup"><span data-stu-id="bbf14-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="bbf14-106">屏幕坐标</span><span class="sxs-lookup"><span data-stu-id="bbf14-106">Screen Coordinates</span></span>  
 <span data-ttu-id="bbf14-107">Windows 窗体应用程序在屏幕坐标中屏幕上指定窗口的位置。</span><span class="sxs-lookup"><span data-stu-id="bbf14-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="bbf14-108">对于屏幕坐标原点是屏幕的左上角。</span><span class="sxs-lookup"><span data-stu-id="bbf14-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="bbf14-109">窗口的完整位置通常描述由<xref:System.Drawing.Rectangle>结构，它包含两个点定义窗口的左上角和右下角的屏幕坐标。</span><span class="sxs-lookup"><span data-stu-id="bbf14-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="bbf14-110">客户端坐标</span><span class="sxs-lookup"><span data-stu-id="bbf14-110">Client Coordinates</span></span>  
 <span data-ttu-id="bbf14-111">Windows 窗体应用程序窗体或控件使用客户端坐标中指定点的位置。</span><span class="sxs-lookup"><span data-stu-id="bbf14-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="bbf14-112">工作区坐标中的源是控件或窗体的工作区的左上角。</span><span class="sxs-lookup"><span data-stu-id="bbf14-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="bbf14-113">客户端坐标可确保在应用程序可以在窗体或控件，而不考虑屏幕上的控件的窗体的位置绘制时使用一致的坐标值。</span><span class="sxs-lookup"><span data-stu-id="bbf14-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="bbf14-114">客户端区域的尺寸，还介绍了通过<xref:System.Drawing.Rectangle>结构，其中包含工作区坐标中的区域。</span><span class="sxs-lookup"><span data-stu-id="bbf14-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="bbf14-115">在所有情况下，该矩形的左上角坐标包含工作区中，而排除右下角坐标。</span><span class="sxs-lookup"><span data-stu-id="bbf14-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="bbf14-116">图形操作不包括的工作区上边缘右和下边缘。</span><span class="sxs-lookup"><span data-stu-id="bbf14-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="bbf14-117">例如<xref:System.Drawing.Graphics.FillRectangle%2A>方法将被填满到指定的矩形中，右和下边缘，但不是会包括这些边缘。</span><span class="sxs-lookup"><span data-stu-id="bbf14-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="bbf14-118">从一种类型的坐标映射到另一个</span><span class="sxs-lookup"><span data-stu-id="bbf14-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="bbf14-119">有时，可能需要从屏幕坐标映射到客户端坐标。</span><span class="sxs-lookup"><span data-stu-id="bbf14-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="bbf14-120">您可以轻松地实现此目的通过使用<xref:System.Windows.Forms.Control.PointToClient%2A>并<xref:System.Windows.Forms.Control.PointToScreen%2A>方法中提供<xref:System.Windows.Forms.Control>类。</span><span class="sxs-lookup"><span data-stu-id="bbf14-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="bbf14-121">例如，<xref:System.Windows.Forms.Control.MousePosition%2A>属性的<xref:System.Windows.Forms.Control>屏幕坐标中报告但你可能想要将它们转换成工作区坐标中。</span><span class="sxs-lookup"><span data-stu-id="bbf14-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf14-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbf14-122">See also</span></span>
- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
