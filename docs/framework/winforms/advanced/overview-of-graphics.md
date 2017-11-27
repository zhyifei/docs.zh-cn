---
title: "图形概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0a3286cbcaa0eebf59500582a749804b5e1b8ba
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="overview-of-graphics"></a><span data-ttu-id="964c4-102">图形概述</span><span class="sxs-lookup"><span data-stu-id="964c4-102">Overview of Graphics</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="964c4-103">是窗体的 Microsoft Windows 操作系统子系统应用程序编程接口 (API)。</span><span class="sxs-lookup"><span data-stu-id="964c4-103"> is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="964c4-104">负责在屏幕和打印机上显示信息。</span><span class="sxs-lookup"><span data-stu-id="964c4-104"> is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="964c4-105">顾名思义，[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 是 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 的后续，后者是包含在 Windows 早期版本中的图形设备接口。</span><span class="sxs-lookup"><span data-stu-id="964c4-105">As its name suggests, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is the successor to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="964c4-106">托管类接口</span><span class="sxs-lookup"><span data-stu-id="964c4-106">Managed Class Interface</span></span>  
 <span data-ttu-id="964c4-107">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API 通过一组部署为托管代码的类公开。</span><span class="sxs-lookup"><span data-stu-id="964c4-107">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="964c4-108">这组类称为*托管的类接口*到[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="964c4-108">This set of classes is called the *managed class interface* to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="964c4-109">以下命名空间构成托管类接口：</span><span class="sxs-lookup"><span data-stu-id="964c4-109">The following namespaces make up the managed class interface:</span></span>  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="964c4-110">使用图形设备接口，如[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，你可以在屏幕或打印机上显示信息，而无需顾虑特定显示设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="964c4-110">With a Graphics Device Interface, such as [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="964c4-111">程序员调用由 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 类提供的方法。</span><span class="sxs-lookup"><span data-stu-id="964c4-111">The programmer makes calls to methods provided by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span> <span data-ttu-id="964c4-112">这些方法，反过来，对特定的设备驱动程序进行适当的调用。</span><span class="sxs-lookup"><span data-stu-id="964c4-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="964c4-113"> 使应用程序与图形硬件隔离。</span><span class="sxs-lookup"><span data-stu-id="964c4-113"> insulates the application from the graphics hardware.</span></span> <span data-ttu-id="964c4-114">它是这种隔离使程序员能够创建独立于设备的应用程序。</span><span class="sxs-lookup"><span data-stu-id="964c4-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="964c4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="964c4-115">See Also</span></span>  
 [<span data-ttu-id="964c4-116">图形概述</span><span class="sxs-lookup"><span data-stu-id="964c4-116">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
