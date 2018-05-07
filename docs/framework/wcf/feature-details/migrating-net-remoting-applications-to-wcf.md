---
title: 将 .NET 远程处理应用程序迁移到 WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 53f63352503a48ee849580e676b5fe98f3dcf2cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>将 .NET 远程处理应用程序迁移到 WCF
**本主题介绍一项传统技术，保留该技术是为了向后兼容现有的应用程序，不建议对新的开发使用该技术。现在应使用 WCF 开发分布式应用程序。**  
  
 有两种方法以利用现有的.NET 远程处理应用程序的 WCF： 集成和迁移。 集成，你可以.Net Remoting 2.0 和运行的 WCF 端并排情况下，让你无需修改现有的.Net 同时通过两种技术公开相同的业务对象 Remoting 2.0 代码。 集成要求运行 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 或更高版本。 如果你想要利用 WCF 功能，并且不需要与 Remoting 2.0 系统的网络兼容性，你可以将整个服务迁移到 WCF。 从.NET Remoting 2.0 迁移到 WCF 需要更改远程对象的接口和其配置设置。 中介绍了这两这些主题[从远程处理与 Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403)。  
  
## <a name="see-also"></a>请参阅  
 [概念性概述](../../../../docs/framework/wcf/conceptual-overview.md)
