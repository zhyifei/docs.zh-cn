---
title: ICLRReferenceAssemblyEnum 接口
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum
helpviewer_keywords:
- ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: 8adbf092-c3ba-4bee-b25b-0de6e43a4ce5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32f27d6c15a99282eee20d2563a4ca741238d846
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638510"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="05e74-102">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="05e74-102">ICLRReferenceAssemblyEnum Interface</span></span>
<span data-ttu-id="05e74-103">提供了使宿主可以操作该集由文件或流使用程序集标识数据，而无需创建或了解这些标识是公共语言运行时 (CLR) 的内部引用的程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="05e74-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05e74-104">方法</span><span class="sxs-lookup"><span data-stu-id="05e74-104">Methods</span></span>  
  
|<span data-ttu-id="05e74-105">方法</span><span class="sxs-lookup"><span data-stu-id="05e74-105">Method</span></span>|<span data-ttu-id="05e74-106">描述</span><span class="sxs-lookup"><span data-stu-id="05e74-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05e74-107">Get 方法</span><span class="sxs-lookup"><span data-stu-id="05e74-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="05e74-108">提供的索引处获取程序集标识。</span><span class="sxs-lookup"><span data-stu-id="05e74-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05e74-109">要求</span><span class="sxs-lookup"><span data-stu-id="05e74-109">Requirements</span></span>  
 <span data-ttu-id="05e74-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05e74-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e74-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05e74-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05e74-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="05e74-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05e74-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05e74-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e74-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="05e74-114">See also</span></span>

- [<span data-ttu-id="05e74-115">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="05e74-115">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="05e74-116">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="05e74-116">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="05e74-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="05e74-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
