---
title: 图形概述
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: a95086645771de61cfc859e34b225992bc16eac9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103924"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="1327a-102">图形概述</span><span class="sxs-lookup"><span data-stu-id="1327a-102">Overview of Graphics</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="1327a-103">是窗体的 Microsoft Windows 操作系统子系统应用程序编程接口 (API)。</span><span class="sxs-lookup"><span data-stu-id="1327a-103">is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="1327a-104">负责在屏幕和打印机上显示的信息。</span><span class="sxs-lookup"><span data-stu-id="1327a-104">is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="1327a-105">顾名思义，[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 是 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 的后续，后者是包含在 Windows 早期版本中的图形设备接口。</span><span class="sxs-lookup"><span data-stu-id="1327a-105">As its name suggests, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is the successor to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="1327a-106">托管类接口</span><span class="sxs-lookup"><span data-stu-id="1327a-106">Managed Class Interface</span></span>  
 <span data-ttu-id="1327a-107">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]通过一组部署为托管代码的类公开 API。</span><span class="sxs-lookup"><span data-stu-id="1327a-107">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="1327a-108">这组类称为*托管的类接口*到[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1327a-108">This set of classes is called the *managed class interface* to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="1327a-109">以下命名空间构成托管类接口：</span><span class="sxs-lookup"><span data-stu-id="1327a-109">The following namespaces make up the managed class interface:</span></span>  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="1327a-110">使用图形设备接口，如[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，可以在屏幕或打印机上显示信息，而无需顾虑特定显示设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1327a-110">With a Graphics Device Interface, such as [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="1327a-111">程序员调用由 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 类提供的方法。</span><span class="sxs-lookup"><span data-stu-id="1327a-111">The programmer makes calls to methods provided by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span> <span data-ttu-id="1327a-112">这些方法，反过来，对特定的设备驱动程序进行适当的调用。</span><span class="sxs-lookup"><span data-stu-id="1327a-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="1327a-113">隔离应用程序从图形硬件。</span><span class="sxs-lookup"><span data-stu-id="1327a-113">insulates the application from the graphics hardware.</span></span> <span data-ttu-id="1327a-114">它是这种隔离使程序员能够创建独立于设备的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1327a-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1327a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1327a-115">See also</span></span>

- [<span data-ttu-id="1327a-116">图形概述</span><span class="sxs-lookup"><span data-stu-id="1327a-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
