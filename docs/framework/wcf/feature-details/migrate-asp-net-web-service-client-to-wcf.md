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
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="5f288-102">如何：将 ASP.NET Web 服务客户端代码迁移到 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5f288-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="5f288-103">以下过程描述需遵循将 ASP.NET Web 服务客户端代码迁移到 WCF 的几大步骤。</span><span class="sxs-lookup"><span data-stu-id="5f288-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to WCF.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="5f288-104">过程</span><span class="sxs-lookup"><span data-stu-id="5f288-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="5f288-105">将 ASP.NET Web 服务客户端代码迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="5f288-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="5f288-106">确保客户端具有综合测试集。</span><span class="sxs-lookup"><span data-stu-id="5f288-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="5f288-107">使用 Visual Studio 2005 将客户端应用程序升级到 .NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="5f288-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="5f288-108">运行测试集。</span><span class="sxs-lookup"><span data-stu-id="5f288-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="5f288-109">从客户端项目中删除 ASP.NET 客户端代码。</span><span class="sxs-lookup"><span data-stu-id="5f288-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="5f288-110">该代码位于使用 WSDL.exe 工具生成的模块中。</span><span class="sxs-lookup"><span data-stu-id="5f288-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="5f288-111">生成 WCF 客户端代码使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="5f288-111">Generate WCF client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="5f288-112">将该代码添加到客户端项目中并将配置输出合并到客户端的现有配置文件中。</span><span class="sxs-lookup"><span data-stu-id="5f288-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="5f288-113">编译该应用程序。</span><span class="sxs-lookup"><span data-stu-id="5f288-113">Compile the application.</span></span> <span data-ttu-id="5f288-114">通过将对以前的 ASP.NET 客户端类型的引用替换为对新的 WCF 客户端类型的引用，修复编译错误。</span><span class="sxs-lookup"><span data-stu-id="5f288-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new WCF client types.</span></span>  
  
6.  <span data-ttu-id="5f288-115">运行测试集。</span><span class="sxs-lookup"><span data-stu-id="5f288-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f288-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f288-116">See Also</span></span>  
 [<span data-ttu-id="5f288-117">如何：将 ASP.NET Web 服务代码迁移到 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5f288-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
