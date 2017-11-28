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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b73274a09ae748cdf1ee33c885de86b1f52c105
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="a7540-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="a7540-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="a7540-103">创建的实例[Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)类。</span><span class="sxs-lookup"><span data-stu-id="a7540-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7540-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7540-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7540-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7540-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="a7540-106">参数值</span><span class="sxs-lookup"><span data-stu-id="a7540-106">Parameter Values</span></span>  
 <span data-ttu-id="a7540-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="a7540-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="a7540-108">描述要在生成的工作流活动中执行的操作，包括操作名称、返回类型和参数信息。</span><span class="sxs-lookup"><span data-stu-id="a7540-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="a7540-109">此参数的值不能**null**。</span><span class="sxs-lookup"><span data-stu-id="a7540-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="a7540-110">它应描述使用消息协定并且取得具有一个消息的参数的同步操作。</span><span class="sxs-lookup"><span data-stu-id="a7540-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="a7540-111">如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。</span><span class="sxs-lookup"><span data-stu-id="a7540-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="a7540-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="a7540-112">*configurationName*</span></span>  
  
 <span data-ttu-id="a7540-113">指定终结点配置名称。</span><span class="sxs-lookup"><span data-stu-id="a7540-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="a7540-114">此参数的值必须不是**null**或为空。</span><span class="sxs-lookup"><span data-stu-id="a7540-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="a7540-115">如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。</span><span class="sxs-lookup"><span data-stu-id="a7540-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="a7540-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="a7540-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="a7540-117">指定操作的服务命名空间。</span><span class="sxs-lookup"><span data-stu-id="a7540-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="a7540-118">此参数的值必须不是**null**或为空。</span><span class="sxs-lookup"><span data-stu-id="a7540-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="a7540-119">如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。</span><span class="sxs-lookup"><span data-stu-id="a7540-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7540-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7540-120">See Also</span></span>  
 [<span data-ttu-id="a7540-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="a7540-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
