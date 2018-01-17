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
ms.workload: dotnet
ms.openlocfilehash: 3438fe2f1c3a6fc40efda0ff2583208f38bf7d5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="overview-of-graphics"></a>图形概述
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]是窗体的 Microsoft Windows 操作系统子系统应用程序编程接口 (API)。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]负责在屏幕和打印机上显示信息。 顾名思义，[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 是 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 的后续，后者是包含在 Windows 早期版本中的图形设备接口。  
  
## <a name="managed-class-interface"></a>托管类接口  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API 通过一组部署为托管代码的类公开。 这组类称为*托管的类接口*到[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。 以下命名空间构成托管类接口：  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 使用图形设备接口，如[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，你可以在屏幕或打印机上显示信息，而无需顾虑特定显示设备的详细信息。 程序员调用由 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 类提供的方法。 这些方法，反过来，对特定的设备驱动程序进行适当的调用。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 使应用程序与图形硬件隔离。 它是这种隔离使程序员能够创建独立于设备的应用程序。  
  
## <a name="see-also"></a>请参阅  
 [图形概述](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
