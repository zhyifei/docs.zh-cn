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
# <a name="overview-of-graphics"></a>图形概述
GDI + 是窗体的 Microsoft Windows 操作系统子系统应用程序编程接口 (API)。 GDI + 是负责在屏幕和打印机上显示的信息。 顾名思义，GDI + 是 GDI，包含与早期版本的 Windows 图形设备接口的后续版本。  
  
## <a name="managed-class-interface"></a>托管类接口  
 GDI + API 通过一组部署为托管代码的类公开。 这组类称为*托管的类接口*GDI +。 以下命名空间构成托管类接口：  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 使用图形设备接口，如 GDI + 中，您可以显示信息屏幕或打印机上而无需顾虑特定显示设备的详细信息。 程序员对 GDI + 类所提供的方法的调用。 这些方法，反过来，对特定的设备驱动程序进行适当的调用。 GDI + 可隔离应用程序从图形硬件。 它是这种隔离使程序员能够创建独立于设备的应用程序。  
  
## <a name="see-also"></a>请参阅

- [图形概述](graphics-overview-windows-forms.md)
