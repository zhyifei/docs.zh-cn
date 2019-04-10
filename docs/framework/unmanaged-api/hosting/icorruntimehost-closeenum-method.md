---
title: ICorRuntimeHost::CloseEnum 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f150fe80302cd03e872ca8bdf5d172caae1ce599
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230767"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="a0ab9-102">ICorRuntimeHost::CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="a0ab9-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="a0ab9-103">将域枚举数重置回域列表的开头。</span><span class="sxs-lookup"><span data-stu-id="a0ab9-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ab9-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0ab9-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0ab9-105">参数</span><span class="sxs-lookup"><span data-stu-id="a0ab9-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a0ab9-106">[in]若要重置枚举器。</span><span class="sxs-lookup"><span data-stu-id="a0ab9-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0ab9-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a0ab9-107">Return Value</span></span>  
  
|<span data-ttu-id="a0ab9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0ab9-108">HRESULT</span></span>|<span data-ttu-id="a0ab9-109">描述</span><span class="sxs-lookup"><span data-stu-id="a0ab9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0ab9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0ab9-110">S_OK</span></span>|<span data-ttu-id="a0ab9-111">操作成功。</span><span class="sxs-lookup"><span data-stu-id="a0ab9-111">The operation was successful.</span></span>|  
|<span data-ttu-id="a0ab9-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a0ab9-112">S_FALSE</span></span>|<span data-ttu-id="a0ab9-113">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="a0ab9-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a0ab9-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0ab9-114">E_FAIL</span></span>|<span data-ttu-id="a0ab9-115">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a0ab9-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a0ab9-116">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="a0ab9-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a0ab9-117">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a0ab9-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0ab9-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0ab9-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0ab9-119">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a0ab9-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0ab9-120">要求</span><span class="sxs-lookup"><span data-stu-id="a0ab9-120">Requirements</span></span>  
 <span data-ttu-id="a0ab9-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0ab9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0ab9-122">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0ab9-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0ab9-123">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a0ab9-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0ab9-124">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a0ab9-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ab9-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0ab9-125">See also</span></span>

- [<span data-ttu-id="a0ab9-126">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="a0ab9-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="a0ab9-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="a0ab9-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
