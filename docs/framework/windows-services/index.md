---
title: 开发 Windows 服务应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: af6e4bf7697b3139f6809295737fdd0d90b7f013
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="developing-windows-service-applications"></a>开发 Windows 服务应用程序
使用 Microsoft Visual Studio 或 Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK，你可以轻松创建服务通过创建作为服务安装的应用程序。 此类型的应用程序称为 Windows 服务。 使用框架功能，可以创建服务、 安装它们，并启动、 停止和以其他方式控制其行为。  
  
> [!WARNING]
>  Visual Studio 2010 中未包括 c + + 的 Windows 服务模板。 若要创建 Windows 服务，你可以在 Visual C# 或 Visual Basic，无法与现有的 c + + 代码，如果需要互操作，在托管代码中创建服务，或可以通过在本机 c + + 创建 Windows 服务[ATL 项目向导](/cpp/atl/reference/atl-project-wizard).  
  
## <a name="in-this-section"></a>本节内容  
 [Windows 服务应用程序介绍](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 概述介绍 Windows 服务应用程序，一种服务，以及服务应用程序与其他常见的项目类型的区别的生存期。  
  
 [演练：在组件设计器中创建 Windows 服务应用程序](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 提供 Visual Basic 和 Visual C# 中创建服务的一个示例。  
  
 [服务应用程序编程体系结构](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 说明在服务编程中使用的语言元素。  
  
 [如何：创建 Windows 服务](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 介绍创建和配置使用 Windows 服务项目模板的 Windows 服务的过程。  
  
## <a name="related-sections"></a>相关章节  
 <xref:System.ServiceProcess.ServiceBase>  
 描述的主要功能<xref:System.ServiceProcess.ServiceBase>类，该类用于创建服务。  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 介绍的功能<xref:System.ServiceProcess.ServiceProcessInstaller>类，该类用于连同<xref:System.ServiceProcess.ServiceInstaller>类用于安装和卸载你的服务。  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 介绍的功能<xref:System.ServiceProcess.ServiceInstaller>类，该类用于连同<xref:System.ServiceProcess.ServiceProcessInstaller>类用于安装和卸载你的服务。  
  
 [NIB 从模板创建项目](http://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 描述项目中这一章以及如何选择它们之间使用的类型。
