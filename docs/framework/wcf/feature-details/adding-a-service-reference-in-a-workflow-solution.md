---
title: 在工作流解决方案中添加服务引用
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 9dcbf779d948f6d295c2a23f5a09efc5ac989cdd
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46536959"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a><span data-ttu-id="4cce4-102">在工作流解决方案中添加服务引用</span><span class="sxs-lookup"><span data-stu-id="4cce4-102">Adding a Service Reference in a Workflow Solution</span></span>

<span data-ttu-id="4cce4-103">在工作流应用程序中添加服务引用后，其工作方式与常规 WCF 应用程序略有不同。</span><span class="sxs-lookup"><span data-stu-id="4cce4-103">Adding a service reference in a workflow application works a little differently than a regular WCF application.</span></span> <span data-ttu-id="4cce4-104">当选择**添加 > 服务引用**和指定服务的 URL、 下载元数据和自定义活动生成，可用于调用 WCF 服务或 WCF 工作流服务添加到的引用。</span><span class="sxs-lookup"><span data-stu-id="4cce4-104">When you select **Add > Service Reference** and specify the URL to the service, the metadata is downloaded and custom activities are generated that allow you to call the WCF service or WCF workflow service you added a reference to.</span></span> <span data-ttu-id="4cce4-105">添加服务引用后，重新生成解决方案，以便构建生成的活动。</span><span class="sxs-lookup"><span data-stu-id="4cce4-105">After adding a service reference, rebuild the solution so the generated activities are built.</span></span> <span data-ttu-id="4cce4-106">之后它们将出现在工作流设计器工具箱中。</span><span class="sxs-lookup"><span data-stu-id="4cce4-106">They will then appear in the workflow designer toolbox.</span></span> <span data-ttu-id="4cce4-107">但是请注意，仅当在工作流解决方案之内添加服务引用时，这才是可行的。</span><span class="sxs-lookup"><span data-stu-id="4cce4-107">Note however, that this will only work if you are adding a service reference within a workflow solution.</span></span> <span data-ttu-id="4cce4-108">以下 web 广播揭示了如何在其他类型的项目中添加服务引用：[从 Web 项目中的工作流调用的 WCF 服务](https://go.microsoft.com/fwlink/?LinkId=207725)。</span><span class="sxs-lookup"><span data-stu-id="4cce4-108">The following web cast shows how to add a service reference in other types of projects: [Calling a WCF Service from a Workflow in a Web Project](https://go.microsoft.com/fwlink/?LinkId=207725).</span></span>

<span data-ttu-id="4cce4-109">添加对包含相同操作名称的服务的两个或多个服务引用会导致出现问题。</span><span class="sxs-lookup"><span data-stu-id="4cce4-109">Adding two or more service references to services that contain the same operation name will cause a problem.</span></span> <span data-ttu-id="4cce4-110">生成的活动将仅调用第一个服务操作。</span><span class="sxs-lookup"><span data-stu-id="4cce4-110">The generated activities will call only the first service operation.</span></span> <span data-ttu-id="4cce4-111">要解决此问题，请重命名服务操作以使其各不相同，或在每个生成的活动中更改终结点配置名称。</span><span class="sxs-lookup"><span data-stu-id="4cce4-111">To work around this issue rename the service operations so they are different or change the endpoint configuration name within each generated activity.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cce4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cce4-112">See Also</span></span>

- [<span data-ttu-id="4cce4-113">工作流服务</span><span class="sxs-lookup"><span data-stu-id="4cce4-113">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="4cce4-114">如何：创建可调用其他工作流服务的工作流服务</span><span class="sxs-lookup"><span data-stu-id="4cce4-114">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)
- [<span data-ttu-id="4cce4-115">从 Web 项目中的工作流调用的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="4cce4-115">Calling a WCF Service from a Workflow in a Web Project</span></span>](https://go.microsoft.com/fwlink/?LinkId=207725)
