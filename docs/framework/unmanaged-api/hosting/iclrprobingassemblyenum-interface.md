---
title: ICLRProbingAssemblyEnum 接口
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 118345f246de3d7ee68d51cf37e8cdea9de1fdba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638523"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="fcc8f-102">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="fcc8f-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="fcc8f-103">提供启用要使用的是公共语言运行时 (CLR) 的内部，无需创建或了解该标识的程序集的标识信息获取程序集的探测标识的主机的方法。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fcc8f-104">方法</span><span class="sxs-lookup"><span data-stu-id="fcc8f-104">Methods</span></span>  
  
|<span data-ttu-id="fcc8f-105">方法</span><span class="sxs-lookup"><span data-stu-id="fcc8f-105">Method</span></span>|<span data-ttu-id="fcc8f-106">描述</span><span class="sxs-lookup"><span data-stu-id="fcc8f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fcc8f-107">Get 方法</span><span class="sxs-lookup"><span data-stu-id="fcc8f-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="fcc8f-108">获取指定索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcc8f-109">备注</span><span class="sxs-lookup"><span data-stu-id="fcc8f-109">Remarks</span></span>  
 <span data-ttu-id="fcc8f-110">等方法[iclrassemblyidentitymanager:: Getprobingassembliesfromreference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)返回`ICLRProbingAssemblyEnum`实例。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcc8f-111">要求</span><span class="sxs-lookup"><span data-stu-id="fcc8f-111">Requirements</span></span>  
 <span data-ttu-id="fcc8f-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc8f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcc8f-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fcc8f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcc8f-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fcc8f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcc8f-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc8f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc8f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcc8f-116">See also</span></span>

- [<span data-ttu-id="fcc8f-117">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="fcc8f-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="fcc8f-118">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="fcc8f-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="fcc8f-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="fcc8f-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
