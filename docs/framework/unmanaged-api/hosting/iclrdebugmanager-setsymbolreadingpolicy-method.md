---
title: ICLRDebugManager::SetSymbolReadingPolicy 方法
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d186c29c409bd6f85a764e3632e2e8e4998b168
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490107"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="be767-102">ICLRDebugManager::SetSymbolReadingPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="be767-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="be767-103">设置用于读取程序数据库 (PDB) 文件的策略。</span><span class="sxs-lookup"><span data-stu-id="be767-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="be767-104">策略将确定是否在调用堆栈中包括行号和文件相关信息。</span><span class="sxs-lookup"><span data-stu-id="be767-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be767-105">语法</span><span class="sxs-lookup"><span data-stu-id="be767-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be767-106">参数</span><span class="sxs-lookup"><span data-stu-id="be767-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="be767-107">[in]成员[ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="be767-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be767-108">返回值</span><span class="sxs-lookup"><span data-stu-id="be767-108">Return Value</span></span>  
  
|<span data-ttu-id="be767-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be767-109">HRESULT</span></span>|<span data-ttu-id="be767-110">描述</span><span class="sxs-lookup"><span data-stu-id="be767-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be767-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="be767-111">S_OK</span></span>|<span data-ttu-id="be767-112">`SetSymbolReadingPolicy` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="be767-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="be767-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="be767-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="be767-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="be767-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="be767-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be767-115">E_FAIL</span></span>|<span data-ttu-id="be767-116">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="be767-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="be767-117">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="be767-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="be767-118">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="be767-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be767-119">要求</span><span class="sxs-lookup"><span data-stu-id="be767-119">Requirements</span></span>  
 <span data-ttu-id="be767-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be767-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be767-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be767-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be767-122">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="be767-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be767-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be767-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be767-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="be767-124">See also</span></span>
- [<span data-ttu-id="be767-125">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="be767-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
