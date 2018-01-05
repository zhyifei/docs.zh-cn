---
title: "重命名 WCF 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2ab3d780f85131fc7adf24c5f420bd5fe643d9e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="5e4c4-102">重命名 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="5e4c4-102">Renaming a WCF Service</span></span>
<span data-ttu-id="5e4c4-103">本主题介绍如何重命名 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-103">This topic describes how you can rename a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="5e4c4-104">重命名 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="5e4c4-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="5e4c4-105">若要在 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 模板中重命名服务，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5e4c4-105">Perform the following steps to rename a service in a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] template,</span></span>  
  
-   <span data-ttu-id="5e4c4-106">更改实现该服务的类的名称。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-106">Change the name of the class that implements the service.</span></span>  
  
-   <span data-ttu-id="5e4c4-107">在该服务的配置文件中，将服务的名称更改为选定的新名称，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="5e4c4-108">配置文件可以是 app.config 或 web.config 文件，具体取决于宿主模型。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   <span data-ttu-id="5e4c4-109">如果服务是 Web 承载的，则该服务使用 *.svc 文件。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-109">If your service is webhosted, it uses an *.svc file.</span></span> <span data-ttu-id="5e4c4-110">打开 svc 文件并修改服务的名称，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="5e4c4-111">由于没有 svc 文件，因此对于自承载的应用程序来说，此步骤不是必需的。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="5e4c4-112">重命名 WCF 服务协定</span><span class="sxs-lookup"><span data-stu-id="5e4c4-112">Renaming a WCF Service Contract</span></span>  
  
-   <span data-ttu-id="5e4c4-113">若要重命名服务协定，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="5e4c4-113">Perform the following steps to rename the service contract,</span></span>  
  
-   <span data-ttu-id="5e4c4-114">更改服务协定的名称。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-114">Change the name of the service contract.</span></span>  
  
-   <span data-ttu-id="5e4c4-115">在该服务的配置文件中，将服务协定的名称更改为选定的新名称，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="5e4c4-116">配置文件可以是 app.config 或 web.config 文件，具体取决于宿主模型。</span><span class="sxs-lookup"><span data-stu-id="5e4c4-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
