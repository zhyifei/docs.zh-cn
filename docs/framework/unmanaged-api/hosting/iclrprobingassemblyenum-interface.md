---
title: "ICLRProbingAssemblyEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum
helpviewer_keywords: ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6d810ab6e62c6df1b00305947de552ecdbe82141
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="5c21e-102">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="5c21e-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="5c21e-103">提供使主机能够通过使用程序集的标识信息内部公共语言运行时 (CLR)，而无需创建或了解该标识来获取程序集的探测标识的方法。</span><span class="sxs-lookup"><span data-stu-id="5c21e-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c21e-104">方法</span><span class="sxs-lookup"><span data-stu-id="5c21e-104">Methods</span></span>  
  
|<span data-ttu-id="5c21e-105">方法</span><span class="sxs-lookup"><span data-stu-id="5c21e-105">Method</span></span>|<span data-ttu-id="5c21e-106">描述</span><span class="sxs-lookup"><span data-stu-id="5c21e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c21e-107">Get 方法</span><span class="sxs-lookup"><span data-stu-id="5c21e-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="5c21e-108">获取指定索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="5c21e-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c21e-109">备注</span><span class="sxs-lookup"><span data-stu-id="5c21e-109">Remarks</span></span>  
 <span data-ttu-id="5c21e-110">等方法[iclrassemblyidentitymanager:: Getprobingassembliesfromreference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)返回`ICLRProbingAssemblyEnum`实例。</span><span class="sxs-lookup"><span data-stu-id="5c21e-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c21e-111">要求</span><span class="sxs-lookup"><span data-stu-id="5c21e-111">Requirements</span></span>  
 <span data-ttu-id="5c21e-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c21e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c21e-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5c21e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c21e-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5c21e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c21e-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c21e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c21e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c21e-116">See Also</span></span>  
 [<span data-ttu-id="5c21e-117">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="5c21e-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="5c21e-118">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="5c21e-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="5c21e-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="5c21e-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
