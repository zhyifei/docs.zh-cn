---
title: "如何：添加数据服务引用（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fa20e9ed0cefbe587bba90ad25d5460592e3ecf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="c8166-102">如何：添加数据服务引用（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="c8166-102">How to: Add a Data Service Reference (WCF Data Services)</span></span>
<span data-ttu-id="c8166-103">你可以使用**添加服务引用**对话框在 Visual Studio 中添加对引用[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c8166-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span> <span data-ttu-id="c8166-104">这使您可以更轻松地在使用 Visual Studio 开发的客户端应用程序中访问数据服务。</span><span class="sxs-lookup"><span data-stu-id="c8166-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="c8166-105">完成此过程后，会基于从数据服务获取的元数据生成数据类。</span><span class="sxs-lookup"><span data-stu-id="c8166-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="c8166-106">有关详细信息，请参阅[生成数据服务客户端库](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="c8166-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>  
  
### <a name="to-add-a-data-service-reference"></a><span data-ttu-id="c8166-107">添加数据服务引用</span><span class="sxs-lookup"><span data-stu-id="c8166-107">To add a data service reference</span></span>  
  
1.  <span data-ttu-id="c8166-108">（可选）如果数据服务不是解决方案的一部分，且未运行，请启动数据服务，并记下数据服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="c8166-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>  
  
2.  <span data-ttu-id="c8166-109">右键单击客户端项目，然后选择**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="c8166-109">Right-click the client project and then select **Add Service Reference**.</span></span>  
  
3.  <span data-ttu-id="c8166-110">如果数据服务当前解决方案的一部分，请单击**发现**。</span><span class="sxs-lookup"><span data-stu-id="c8166-110">If the data service is part of the current solution, click **Discover**.</span></span>  
  
     <span data-ttu-id="c8166-111">或</span><span class="sxs-lookup"><span data-stu-id="c8166-111">-or-</span></span>  
  
     <span data-ttu-id="c8166-112">在**地址**文本框中，键入数据服务的基 URL 如`http://localhost:1234/Northwind.svc`，然后单击**转**。</span><span class="sxs-lookup"><span data-stu-id="c8166-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>  
  
4.  <span data-ttu-id="c8166-113">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="c8166-113">Click **OK**.</span></span>  
  
     <span data-ttu-id="c8166-114">这样会添加一个新的代码文件，该文件包含用于访问作为对象的数据服务资源并与其交互的数据类。</span><span class="sxs-lookup"><span data-stu-id="c8166-114">This adds a new code file that contains the data classes that are used to access and interact with data service resources as objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8166-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8166-115">See Also</span></span>  
 [<span data-ttu-id="c8166-116">快速入门</span><span class="sxs-lookup"><span data-stu-id="c8166-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
