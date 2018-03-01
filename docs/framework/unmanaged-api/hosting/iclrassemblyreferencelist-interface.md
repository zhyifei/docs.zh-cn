---
title: "ICLRAssemblyReferenceList 接口"
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
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eeef0e7f825f4a6ad907d6b17b92afe1807bad12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="33b18-102">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="33b18-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="33b18-103">管理由公共语言运行时 (CLR) 而不是主机加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="33b18-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33b18-104">方法</span><span class="sxs-lookup"><span data-stu-id="33b18-104">Methods</span></span>  
  
|<span data-ttu-id="33b18-105">方法</span><span class="sxs-lookup"><span data-stu-id="33b18-105">Method</span></span>|<span data-ttu-id="33b18-106">描述</span><span class="sxs-lookup"><span data-stu-id="33b18-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33b18-107">IsAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="33b18-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="33b18-108">获取一个值，该值指示所提供的指针是否引用列表中的程序集。</span><span class="sxs-lookup"><span data-stu-id="33b18-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="33b18-109">IsStringAssemblyReferenceInList 方法</span><span class="sxs-lookup"><span data-stu-id="33b18-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="33b18-110">获取一个值，该值指示所提供的名称是否与列表中的程序集的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="33b18-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33b18-111">备注</span><span class="sxs-lookup"><span data-stu-id="33b18-111">Remarks</span></span>  
 <span data-ttu-id="33b18-112">调用[iclrassemblyidentitymanager:: Getclrassemblyreferencelist](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)方法以获取指向的实例的指针`ICLRAssemblyReferenceList`。</span><span class="sxs-lookup"><span data-stu-id="33b18-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33b18-113">惠?</span><span class="sxs-lookup"><span data-stu-id="33b18-113">Requirements</span></span>  
 <span data-ttu-id="33b18-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33b18-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33b18-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33b18-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33b18-116">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="33b18-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33b18-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33b18-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b18-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="33b18-118">See Also</span></span>  
 [<span data-ttu-id="33b18-119">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="33b18-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="33b18-120">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="33b18-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="33b18-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="33b18-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
