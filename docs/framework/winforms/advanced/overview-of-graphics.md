---
title: 图形概述
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: f0e2fd9dcf31e5fdce16b5a3b6fd21eab6eab66a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505320"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="c892e-102">图形概述</span><span class="sxs-lookup"><span data-stu-id="c892e-102">Overview of Graphics</span></span>
<span data-ttu-id="c892e-103">GDI + 是窗体的 Microsoft Windows 操作系统子系统应用程序编程接口 (API)。</span><span class="sxs-lookup"><span data-stu-id="c892e-103">GDI+ is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> <span data-ttu-id="c892e-104">GDI + 是负责在屏幕和打印机上显示的信息。</span><span class="sxs-lookup"><span data-stu-id="c892e-104">GDI+ is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="c892e-105">顾名思义，GDI + 是 GDI，包含与早期版本的 Windows 图形设备接口的后续版本。</span><span class="sxs-lookup"><span data-stu-id="c892e-105">As its name suggests, GDI+ is the successor to GDI, the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="c892e-106">托管类接口</span><span class="sxs-lookup"><span data-stu-id="c892e-106">Managed Class Interface</span></span>  
 <span data-ttu-id="c892e-107">GDI + API 通过一组部署为托管代码的类公开。</span><span class="sxs-lookup"><span data-stu-id="c892e-107">The GDI+ API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="c892e-108">这组类称为*托管的类接口*GDI +。</span><span class="sxs-lookup"><span data-stu-id="c892e-108">This set of classes is called the *managed class interface* to GDI+.</span></span> <span data-ttu-id="c892e-109">以下命名空间构成托管类接口：</span><span class="sxs-lookup"><span data-stu-id="c892e-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="c892e-110">使用图形设备接口，如 GDI + 中，您可以显示信息屏幕或打印机上而无需顾虑特定显示设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c892e-110">With a Graphics Device Interface, such as GDI+, you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="c892e-111">程序员对 GDI + 类所提供的方法的调用。</span><span class="sxs-lookup"><span data-stu-id="c892e-111">The programmer makes calls to methods provided by GDI+ classes.</span></span> <span data-ttu-id="c892e-112">这些方法，反过来，对特定的设备驱动程序进行适当的调用。</span><span class="sxs-lookup"><span data-stu-id="c892e-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> <span data-ttu-id="c892e-113">GDI + 可隔离应用程序从图形硬件。</span><span class="sxs-lookup"><span data-stu-id="c892e-113">GDI+ insulates the application from the graphics hardware.</span></span> <span data-ttu-id="c892e-114">它是这种隔离使程序员能够创建独立于设备的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c892e-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c892e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c892e-115">See also</span></span>

- [<span data-ttu-id="c892e-116">图形概述</span><span class="sxs-lookup"><span data-stu-id="c892e-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
