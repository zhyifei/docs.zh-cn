---
title: 如何：将 ASP.NET Web 服务客户端代码迁移到 Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
ms.openlocfilehash: cb60f9cb2e8f35ee703b049eae9e3d99c1ec7d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491125"
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>如何：将 ASP.NET Web 服务客户端代码迁移到 Windows Communication Foundation
以下过程描述需遵循将 ASP.NET Web 服务客户端代码迁移到 WCF 的几大步骤。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>将 ASP.NET Web 服务客户端代码迁移到 WCF  
  
1.  确保客户端具有综合测试集。  
  
2.  使用 Visual Studio 2005 将客户端应用程序升级到 .NET 2.0。 运行测试集。  
  
3.  从客户端项目中删除 ASP.NET 客户端代码。 该代码位于使用 WSDL.exe 工具生成的模块中。  
  
4.  生成 WCF 客户端代码使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。 将该代码添加到客户端项目中并将配置输出合并到客户端的现有配置文件中。  
  
5.  编译该应用程序。 通过将对以前的 ASP.NET 客户端类型的引用替换为对新的 WCF 客户端类型的引用，修复编译错误。  
  
6.  运行测试集。  
  
## <a name="see-also"></a>请参阅  
 [如何：将 ASP.NET Web 服务代码迁移到 Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
