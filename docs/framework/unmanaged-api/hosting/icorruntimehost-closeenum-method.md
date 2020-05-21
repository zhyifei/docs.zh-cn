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
ms.openlocfilehash: a5a86df3ac1f50ca624490ad80a6fed903433436
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762365"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="d9265-102">ICorRuntimeHost::CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="d9265-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="d9265-103">将域枚举器重置回域列表的开头。</span><span class="sxs-lookup"><span data-stu-id="d9265-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9265-104">语法</span><span class="sxs-lookup"><span data-stu-id="d9265-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9265-105">参数</span><span class="sxs-lookup"><span data-stu-id="d9265-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d9265-106">中要重置的枚举数。</span><span class="sxs-lookup"><span data-stu-id="d9265-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9265-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d9265-107">Return Value</span></span>  
  
|<span data-ttu-id="d9265-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9265-108">HRESULT</span></span>|<span data-ttu-id="d9265-109">说明</span><span class="sxs-lookup"><span data-stu-id="d9265-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9265-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9265-110">S_OK</span></span>|<span data-ttu-id="d9265-111">操作成功。</span><span class="sxs-lookup"><span data-stu-id="d9265-111">The operation was successful.</span></span>|  
|<span data-ttu-id="d9265-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d9265-112">S_FALSE</span></span>|<span data-ttu-id="d9265-113">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="d9265-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d9265-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9265-114">E_FAIL</span></span>|<span data-ttu-id="d9265-115">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d9265-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d9265-116">如果方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d9265-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="d9265-117">对任何宿主 Api 的后续调用都会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d9265-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d9265-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9265-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9265-119">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d9265-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9265-120">要求</span><span class="sxs-lookup"><span data-stu-id="d9265-120">Requirements</span></span>  
 <span data-ttu-id="d9265-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9265-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9265-122">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d9265-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9265-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d9265-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9265-124">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="d9265-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9265-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9265-125">See also</span></span>

- [<span data-ttu-id="d9265-126">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="d9265-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="d9265-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="d9265-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
