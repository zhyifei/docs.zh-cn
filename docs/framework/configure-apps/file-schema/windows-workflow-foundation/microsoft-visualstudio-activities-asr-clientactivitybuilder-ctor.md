---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location: Microsoft.VisualStudio.Activities.dll
api_type: Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c50d9754b71386e6809d46cd9666987a704fbf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="95a6e-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="95a6e-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="95a6e-103">创建的实例[Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)类。</span><span class="sxs-lookup"><span data-stu-id="95a6e-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95a6e-104">语法</span><span class="sxs-lookup"><span data-stu-id="95a6e-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95a6e-105">参数</span><span class="sxs-lookup"><span data-stu-id="95a6e-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="95a6e-106">参数值</span><span class="sxs-lookup"><span data-stu-id="95a6e-106">Parameter Values</span></span>  
 <span data-ttu-id="95a6e-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="95a6e-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="95a6e-108">描述要在生成的工作流活动中执行的操作，包括操作名称、返回类型和参数信息。</span><span class="sxs-lookup"><span data-stu-id="95a6e-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="95a6e-109">此参数的值不能**null**。</span><span class="sxs-lookup"><span data-stu-id="95a6e-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="95a6e-110">它应描述使用消息协定并且取得具有一个消息的参数的同步操作。</span><span class="sxs-lookup"><span data-stu-id="95a6e-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="95a6e-111">如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。</span><span class="sxs-lookup"><span data-stu-id="95a6e-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="95a6e-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="95a6e-112">*configurationName*</span></span>  
  
 <span data-ttu-id="95a6e-113">指定终结点配置名称。</span><span class="sxs-lookup"><span data-stu-id="95a6e-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="95a6e-114">此参数的值必须不是**null**或为空。</span><span class="sxs-lookup"><span data-stu-id="95a6e-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="95a6e-115">如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。</span><span class="sxs-lookup"><span data-stu-id="95a6e-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="95a6e-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="95a6e-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="95a6e-117">指定操作的服务命名空间。</span><span class="sxs-lookup"><span data-stu-id="95a6e-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="95a6e-118">此参数的值必须不是**null**或为空。</span><span class="sxs-lookup"><span data-stu-id="95a6e-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="95a6e-119">如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。</span><span class="sxs-lookup"><span data-stu-id="95a6e-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95a6e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="95a6e-120">See Also</span></span>  
 [<span data-ttu-id="95a6e-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="95a6e-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
