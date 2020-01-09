---
title: ICorRuntimeHost::Start 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: c450d83669a3bc548c15ed5800dc73438b9a84a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127684"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="ece49-102">ICorRuntimeHost::Start 方法</span><span class="sxs-lookup"><span data-stu-id="ece49-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="ece49-103">启动公共语言运行时（CLR）。</span><span class="sxs-lookup"><span data-stu-id="ece49-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ece49-104">语法</span><span class="sxs-lookup"><span data-stu-id="ece49-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ece49-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ece49-105">Return Value</span></span>  
  
|<span data-ttu-id="ece49-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ece49-106">HRESULT</span></span>|<span data-ttu-id="ece49-107">描述</span><span class="sxs-lookup"><span data-stu-id="ece49-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ece49-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ece49-108">S_OK</span></span>|<span data-ttu-id="ece49-109">操作成功。</span><span class="sxs-lookup"><span data-stu-id="ece49-109">The operation was successful.</span></span>|  
|<span data-ttu-id="ece49-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ece49-110">S_FALSE</span></span>|<span data-ttu-id="ece49-111">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="ece49-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ece49-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ece49-112">E_FAIL</span></span>|<span data-ttu-id="ece49-113">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ece49-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ece49-114">如果某个方法返回 E_FAIL，则 CLR 将无法再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="ece49-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="ece49-115">对任何托管 Api 的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ece49-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ece49-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ece49-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ece49-117">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ece49-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ece49-118">备注</span><span class="sxs-lookup"><span data-stu-id="ece49-118">Remarks</span></span>  
 <span data-ttu-id="ece49-119">通常不需要调用 `Start` 方法，因为 CLR 会在首次运行托管代码的请求时自动启动。</span><span class="sxs-lookup"><span data-stu-id="ece49-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ece49-120">要求</span><span class="sxs-lookup"><span data-stu-id="ece49-120">Requirements</span></span>  
 <span data-ttu-id="ece49-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ece49-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ece49-122">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ece49-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ece49-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ece49-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ece49-124">**.NET Framework 版本：** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="ece49-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece49-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ece49-125">See also</span></span>

- [<span data-ttu-id="ece49-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="ece49-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
