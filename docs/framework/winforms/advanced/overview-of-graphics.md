---
title: 图形概述
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: 927fc327d9ad42cd3a99af207d04efbc520df8b5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645706"
---
# <a name="overview-of-graphics"></a>图形概述
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 是窗体的 Microsoft Windows 操作系统子系统应用程序编程接口 (API)。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 负责在屏幕和打印机上显示的信息。 顾名思义，[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 是 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 的后续，后者是包含在 Windows 早期版本中的图形设备接口。  
  
## <a name="managed-class-interface"></a>托管类接口  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]通过一组部署为托管代码的类公开 API。 这组类称为*托管的类接口*到[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。 以下命名空间构成托管类接口：  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 使用图形设备接口，如[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，可以在屏幕或打印机上显示信息，而无需顾虑特定显示设备的详细信息。 程序员调用由 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 类提供的方法。 这些方法，反过来，对特定的设备驱动程序进行适当的调用。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 使应用程序与图形硬件隔离。 它是这种隔离使程序员能够创建独立于设备的应用程序。  
  
## <a name="see-also"></a>请参阅

- [图形概述](graphics-overview-windows-forms.md)
