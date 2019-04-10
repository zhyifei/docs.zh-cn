---
title: 如何：部署 COM+ 集成应用程序
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: fcf525943e6e453253c6f4d3bcfa8a1a08df6909
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343371"
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="2d9fe-102">如何：部署 COM+ 集成应用程序</span><span class="sxs-lookup"><span data-stu-id="2d9fe-102">How to: Deploy a COM+ Integration Application</span></span>
<span data-ttu-id="2d9fe-103">编写了 COM+ 集成应用程序后，您可能要将它部署在另一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="2d9fe-104">本主题说明如何将 COM+ 集成应用程序从一台计算机移动到另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="2d9fe-105">移动 COM+ 承载的集成应用程序</span><span class="sxs-lookup"><span data-stu-id="2d9fe-105">Moving a COM+ hosted Integration App</span></span>  
  
1. <span data-ttu-id="2d9fe-106">请确保这两台计算机上安装了 WCF。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-106">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="2d9fe-107">从计算机 A 中导出应用程序。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-107">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="2d9fe-108">在计算机 B 上导入应用程序。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-108">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="2d9fe-109">设置应用程序根目录。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-109">Set the Application Root Directory.</span></span> <span data-ttu-id="2d9fe-110">按照约定，此目录为 %PROGRAMFILES%/ComPlus Applications/{AppGUID}。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5. <span data-ttu-id="2d9fe-111">将计算机 A 上应用程序根目录中的 Application.config 和 Application.manifest 文件复制到计算机 B 上的应用程序根目录。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6. <span data-ttu-id="2d9fe-112">在计算机 B 的 Application.config 文件中编辑服务终结点地址以标识相应计算机。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="2d9fe-113">例如，将 `http://machineA/MyService` 更改为 `http://machineB/MyService`。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-113">For example, change `http://machineA/MyService` to `http://machineB/MyService`.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="2d9fe-114">移动 Web 承载的集成应用程序</span><span class="sxs-lookup"><span data-stu-id="2d9fe-114">Moving a Web-hosted integration application</span></span>  
  
1. <span data-ttu-id="2d9fe-115">请确保这两台计算机上安装了 WCF。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-115">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="2d9fe-116">从计算机 A 中导出应用程序。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-116">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="2d9fe-117">在计算机 B 上导入应用程序。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-117">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="2d9fe-118">在计算机 B 上创建 IIS 虚拟根目录。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-118">Create an IIS vroot on machine B.</span></span>  
  
5. <span data-ttu-id="2d9fe-119">将计算机 A 上虚拟根目录中的 .svc 文件 (componentName.svc) 和 Web.config 文件复制到计算机 B 上新创建的虚拟根目录。</span><span class="sxs-lookup"><span data-stu-id="2d9fe-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d9fe-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d9fe-120">See also</span></span>

- [<span data-ttu-id="2d9fe-121">与 COM+ 应用程序集成的概述</span><span class="sxs-lookup"><span data-stu-id="2d9fe-121">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)
- [<span data-ttu-id="2d9fe-122">如何：配置 COM+ 服务设置</span><span class="sxs-lookup"><span data-stu-id="2d9fe-122">How to: Configure COM+ Service Settings</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
- [<span data-ttu-id="2d9fe-123">如何：使用 COM+ 服务模型配置工具</span><span class="sxs-lookup"><span data-stu-id="2d9fe-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
