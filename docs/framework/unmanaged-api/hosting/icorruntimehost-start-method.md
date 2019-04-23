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
ms.openlocfilehash: 5e6521f8013bf92f073ab4b6808871c95ac2802b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072852"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="d03be-102">ICorRuntimeHost::Start 方法</span><span class="sxs-lookup"><span data-stu-id="d03be-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="d03be-103">启动公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="d03be-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d03be-104">语法</span><span class="sxs-lookup"><span data-stu-id="d03be-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d03be-105">返回值</span><span class="sxs-lookup"><span data-stu-id="d03be-105">Return Value</span></span>  
  
|<span data-ttu-id="d03be-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d03be-106">HRESULT</span></span>|<span data-ttu-id="d03be-107">描述</span><span class="sxs-lookup"><span data-stu-id="d03be-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d03be-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d03be-108">S_OK</span></span>|<span data-ttu-id="d03be-109">操作成功。</span><span class="sxs-lookup"><span data-stu-id="d03be-109">The operation was successful.</span></span>|  
|<span data-ttu-id="d03be-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d03be-110">S_FALSE</span></span>|<span data-ttu-id="d03be-111">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="d03be-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d03be-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d03be-112">E_FAIL</span></span>|<span data-ttu-id="d03be-113">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d03be-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d03be-114">如果方法返回 E_FAIL，CLR 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="d03be-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="d03be-115">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d03be-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d03be-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d03be-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d03be-117">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d03be-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d03be-118">备注</span><span class="sxs-lookup"><span data-stu-id="d03be-118">Remarks</span></span>  
 <span data-ttu-id="d03be-119">通常是不需要调用`Start`方法，因为 CLR 运行托管的代码在第一个请求时自动启动。</span><span class="sxs-lookup"><span data-stu-id="d03be-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d03be-120">要求</span><span class="sxs-lookup"><span data-stu-id="d03be-120">Requirements</span></span>  
 <span data-ttu-id="d03be-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d03be-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d03be-122">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d03be-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d03be-123">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d03be-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d03be-124">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d03be-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d03be-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="d03be-125">See also</span></span>

- [<span data-ttu-id="d03be-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="d03be-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
