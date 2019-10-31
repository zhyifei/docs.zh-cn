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
ms.openlocfilehash: 6737b953f39c1087d01f3fb864d84340a6968aba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129359"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="86513-102">ICLRDebugManager::SetSymbolReadingPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="86513-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="86513-103">设置用于读取程序数据库（PDB）文件的策略。</span><span class="sxs-lookup"><span data-stu-id="86513-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="86513-104">策略确定有关行号和文件的信息是否包含在调用堆栈中。</span><span class="sxs-lookup"><span data-stu-id="86513-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86513-105">语法</span><span class="sxs-lookup"><span data-stu-id="86513-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86513-106">参数</span><span class="sxs-lookup"><span data-stu-id="86513-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="86513-107">中[ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md)枚举的成员。</span><span class="sxs-lookup"><span data-stu-id="86513-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86513-108">返回值</span><span class="sxs-lookup"><span data-stu-id="86513-108">Return Value</span></span>  
  
|<span data-ttu-id="86513-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86513-109">HRESULT</span></span>|<span data-ttu-id="86513-110">描述</span><span class="sxs-lookup"><span data-stu-id="86513-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86513-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="86513-111">S_OK</span></span>|<span data-ttu-id="86513-112">`SetSymbolReadingPolicy` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="86513-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="86513-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86513-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86513-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="86513-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="86513-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86513-115">E_FAIL</span></span>|<span data-ttu-id="86513-116">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="86513-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="86513-117">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="86513-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86513-118">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="86513-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86513-119">要求</span><span class="sxs-lookup"><span data-stu-id="86513-119">Requirements</span></span>  
 <span data-ttu-id="86513-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86513-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86513-121">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="86513-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86513-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="86513-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86513-123">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86513-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86513-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="86513-124">See also</span></span>

- [<span data-ttu-id="86513-125">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="86513-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
