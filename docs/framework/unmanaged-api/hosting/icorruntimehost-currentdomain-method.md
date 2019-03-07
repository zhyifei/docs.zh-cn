---
title: ICorRuntimeHost::CurrentDomain 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0230f2e313b6d84b2c249afb28f7c5fdf34fdd0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479657"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="caff9-102">ICorRuntimeHost::CurrentDomain 方法</span><span class="sxs-lookup"><span data-stu-id="caff9-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="caff9-103">获取类型的接口指针<xref:System.AppDomain?displayProperty=nameWithType>，表示当前线程上加载的域。</span><span class="sxs-lookup"><span data-stu-id="caff9-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caff9-104">语法</span><span class="sxs-lookup"><span data-stu-id="caff9-104">Syntax</span></span>  
  
```  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caff9-105">参数</span><span class="sxs-lookup"><span data-stu-id="caff9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="caff9-106">[out]类型的指针<xref:System.AppDomain?displayProperty=nameWithType>，表示线程的当前应用程序域。</span><span class="sxs-lookup"><span data-stu-id="caff9-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="caff9-107">此指针被类型化为`IUnknown`，因此调用方通常应调用`QueryInterface`若要获取类型的指针<xref:System._AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="caff9-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="caff9-108">返回值</span><span class="sxs-lookup"><span data-stu-id="caff9-108">Return Value</span></span>  
  
|<span data-ttu-id="caff9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="caff9-109">HRESULT</span></span>|<span data-ttu-id="caff9-110">描述</span><span class="sxs-lookup"><span data-stu-id="caff9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="caff9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="caff9-111">S_OK</span></span>|<span data-ttu-id="caff9-112">操作成功。</span><span class="sxs-lookup"><span data-stu-id="caff9-112">The operation was successful.</span></span>|  
|<span data-ttu-id="caff9-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="caff9-113">S_FALSE</span></span>|<span data-ttu-id="caff9-114">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="caff9-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="caff9-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="caff9-115">E_FAIL</span></span>|<span data-ttu-id="caff9-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="caff9-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="caff9-117">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="caff9-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="caff9-118">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="caff9-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="caff9-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="caff9-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="caff9-120">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="caff9-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="caff9-121">要求</span><span class="sxs-lookup"><span data-stu-id="caff9-121">Requirements</span></span>  
 <span data-ttu-id="caff9-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="caff9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caff9-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="caff9-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="caff9-124">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="caff9-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="caff9-125">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="caff9-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caff9-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="caff9-126">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="caff9-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="caff9-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
