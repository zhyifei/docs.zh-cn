---
title: "IDefinitionAppId 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 247edbe300bbb93ddbdd4260109999fd33b08006
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="3da3e-102">IDefinitionAppId 接口</span><span class="sxs-lookup"><span data-stu-id="3da3e-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="3da3e-103">表示在当前范围内定义应用程序的代码的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3da3e-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3da3e-104">方法</span><span class="sxs-lookup"><span data-stu-id="3da3e-104">Methods</span></span>  
  
|<span data-ttu-id="3da3e-105">方法</span><span class="sxs-lookup"><span data-stu-id="3da3e-105">Method</span></span>|<span data-ttu-id="3da3e-106">描述</span><span class="sxs-lookup"><span data-stu-id="3da3e-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="3da3e-107">获取表示在此代码的格式化的字符串`IDefinitionAppId`对象。</span><span class="sxs-lookup"><span data-stu-id="3da3e-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="3da3e-108">设置此代码`IDefinitionAppId`到指定的对象设置格式的字符串值。</span><span class="sxs-lookup"><span data-stu-id="3da3e-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="3da3e-109">获取到的接口指针[IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)对象，其中包含当前的应用程序路径中的程序集。</span><span class="sxs-lookup"><span data-stu-id="3da3e-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="3da3e-110">为程序集的应用程序路径设置到由指定引用的值的当前作用域中[IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="3da3e-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="3da3e-111">获取一个指针指向的字符串表示形式的令牌标识符对此订阅`IDefinitionAppId`对象。</span><span class="sxs-lookup"><span data-stu-id="3da3e-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="3da3e-112">设置与此订阅的令牌标识符`IDefinitionAppId`到指定的字符串值的对象。</span><span class="sxs-lookup"><span data-stu-id="3da3e-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3da3e-113">惠?</span><span class="sxs-lookup"><span data-stu-id="3da3e-113">Requirements</span></span>  
 <span data-ttu-id="3da3e-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3da3e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da3e-115">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="3da3e-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="3da3e-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3da3e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da3e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3da3e-117">See Also</span></span>  
 [<span data-ttu-id="3da3e-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="3da3e-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
