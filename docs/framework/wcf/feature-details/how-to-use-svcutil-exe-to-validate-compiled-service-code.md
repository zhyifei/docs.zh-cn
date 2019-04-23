---
title: 如何：使用 Svcutil.exe 验证已编译的服务代码
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 599f5624b7eb0c32cbcc0a78e6c7f989ce470b58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312418"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="19443-102">如何：使用 Svcutil.exe 验证已编译的服务代码</span><span class="sxs-lookup"><span data-stu-id="19443-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="19443-103">可以使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)不承载服务的情况下检测服务实现和配置中的错误。</span><span class="sxs-lookup"><span data-stu-id="19443-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="19443-104">验证服务</span><span class="sxs-lookup"><span data-stu-id="19443-104">To validate a service</span></span>  
  
1. <span data-ttu-id="19443-105">将服务编译为可执行文件以及一个或多个相关程序集。</span><span class="sxs-lookup"><span data-stu-id="19443-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2. <span data-ttu-id="19443-106">打开一个 SDK 命令提示</span><span class="sxs-lookup"><span data-stu-id="19443-106">Open an SDK command prompt</span></span>  
  
3. <span data-ttu-id="19443-107">在命令提示符处，使用下面的格式启动 Svcutil.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="19443-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="19443-108">有关各种参数的详细信息，请参阅的服务 Validationsection [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)主题。</span><span class="sxs-lookup"><span data-stu-id="19443-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="19443-109">必须使用 `/serviceName` 选项来指示要验证的服务的配置名称。</span><span class="sxs-lookup"><span data-stu-id="19443-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="19443-110">`assemblyPath` 自变量指定一个路径，该路径指向包含要验证的服务类型的服务以及一个或多个程序集的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="19443-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="19443-111">可执行程序集必须具有关联的配置文件，以提供服务配置。</span><span class="sxs-lookup"><span data-stu-id="19443-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="19443-112">可以使用标准命令行通配符来提供多个程序集。</span><span class="sxs-lookup"><span data-stu-id="19443-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19443-113">示例</span><span class="sxs-lookup"><span data-stu-id="19443-113">Example</span></span>  
 <span data-ttu-id="19443-114">下面的命令验证在 myServiceHost.exe 可执行文件中实现的服务 myServiceName。</span><span class="sxs-lookup"><span data-stu-id="19443-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="19443-115">该服务的配置文件 (myServiceHost.exe.config) 自动进行加载。</span><span class="sxs-lookup"><span data-stu-id="19443-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="19443-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="19443-116">See also</span></span>

- [<span data-ttu-id="19443-117">ServiceModel 元数据实用工具 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="19443-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
