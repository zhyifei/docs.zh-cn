---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: 0ce9be30182f9181bcb6449529d9b9796aadbc2b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133531"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="2fb51-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="2fb51-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="2fb51-103">创建的实例[Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)类。</span><span class="sxs-lookup"><span data-stu-id="2fb51-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fb51-104">语法</span><span class="sxs-lookup"><span data-stu-id="2fb51-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fb51-105">参数</span><span class="sxs-lookup"><span data-stu-id="2fb51-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="2fb51-106">参数值</span><span class="sxs-lookup"><span data-stu-id="2fb51-106">Parameter Values</span></span>  
 <span data-ttu-id="2fb51-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="2fb51-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="2fb51-108">描述要在生成的工作流活动中执行的操作，包括操作名称、返回类型和参数信息。</span><span class="sxs-lookup"><span data-stu-id="2fb51-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="2fb51-109">此参数的值不能**null**。</span><span class="sxs-lookup"><span data-stu-id="2fb51-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="2fb51-110">它应描述使用消息协定并且取得具有一个消息的参数的同步操作。</span><span class="sxs-lookup"><span data-stu-id="2fb51-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="2fb51-111">如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。</span><span class="sxs-lookup"><span data-stu-id="2fb51-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="2fb51-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="2fb51-112">*configurationName*</span></span>  
  
 <span data-ttu-id="2fb51-113">指定终结点配置名称。</span><span class="sxs-lookup"><span data-stu-id="2fb51-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="2fb51-114">此参数的值不能是**null**或为空。</span><span class="sxs-lookup"><span data-stu-id="2fb51-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="2fb51-115">如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。</span><span class="sxs-lookup"><span data-stu-id="2fb51-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="2fb51-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="2fb51-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="2fb51-117">指定操作的服务命名空间。</span><span class="sxs-lookup"><span data-stu-id="2fb51-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="2fb51-118">此参数的值不能是**null**或为空。</span><span class="sxs-lookup"><span data-stu-id="2fb51-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="2fb51-119">如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。</span><span class="sxs-lookup"><span data-stu-id="2fb51-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fb51-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fb51-120">See also</span></span>

- [<span data-ttu-id="2fb51-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="2fb51-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
