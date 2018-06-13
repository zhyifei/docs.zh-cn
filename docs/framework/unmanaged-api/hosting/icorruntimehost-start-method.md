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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96e8d80e2dff88aa5a589f864278b4a4e9cc76ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437009"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="3fb3e-102">ICorRuntimeHost::Start 方法</span><span class="sxs-lookup"><span data-stu-id="3fb3e-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="3fb3e-103">启动公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="3fb3e-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb3e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3fb3e-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3fb3e-105">返回值</span><span class="sxs-lookup"><span data-stu-id="3fb3e-105">Return Value</span></span>  
  
|<span data-ttu-id="3fb3e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fb3e-106">HRESULT</span></span>|<span data-ttu-id="3fb3e-107">描述</span><span class="sxs-lookup"><span data-stu-id="3fb3e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fb3e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fb3e-108">S_OK</span></span>|<span data-ttu-id="3fb3e-109">该操作成功。</span><span class="sxs-lookup"><span data-stu-id="3fb3e-109">The operation was successful.</span></span>|  
|<span data-ttu-id="3fb3e-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3fb3e-110">S_FALSE</span></span>|<span data-ttu-id="3fb3e-111">操作无法完成。</span><span class="sxs-lookup"><span data-stu-id="3fb3e-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="3fb3e-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3fb3e-112">E_FAIL</span></span>|<span data-ttu-id="3fb3e-113">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3fb3e-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3fb3e-114">如果某方法返回 E_FAIL，CLR 不再在过程中可用。</span><span class="sxs-lookup"><span data-stu-id="3fb3e-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="3fb3e-115">对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3fb3e-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3fb3e-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3fb3e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3fb3e-117">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3fb3e-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fb3e-118">备注</span><span class="sxs-lookup"><span data-stu-id="3fb3e-118">Remarks</span></span>  
 <span data-ttu-id="3fb3e-119">它通常是不需要调用`Start`方法，因为 CLR 将运行托管的代码在第一个请求时自动启动。</span><span class="sxs-lookup"><span data-stu-id="3fb3e-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fb3e-120">要求</span><span class="sxs-lookup"><span data-stu-id="3fb3e-120">Requirements</span></span>  
 <span data-ttu-id="3fb3e-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fb3e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fb3e-122">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fb3e-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fb3e-123">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3fb3e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fb3e-124">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="3fb3e-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb3e-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fb3e-125">See Also</span></span>  
 [<span data-ttu-id="3fb3e-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="3fb3e-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
