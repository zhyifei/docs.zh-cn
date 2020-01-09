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
ms.openlocfilehash: f2249d10159b1ff0be7ead0783efb8a2742d26b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139605"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="75cc2-102">ICorRuntimeHost::CurrentDomain 方法</span><span class="sxs-lookup"><span data-stu-id="75cc2-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="75cc2-103">获取 <xref:System.AppDomain?displayProperty=nameWithType> 类型的接口指针，该指针表示当前线程上加载的域。</span><span class="sxs-lookup"><span data-stu-id="75cc2-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75cc2-104">语法</span><span class="sxs-lookup"><span data-stu-id="75cc2-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75cc2-105">参数</span><span class="sxs-lookup"><span data-stu-id="75cc2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="75cc2-106">弄类型 <xref:System.AppDomain?displayProperty=nameWithType> 的指针，表示线程的当前应用程序域。</span><span class="sxs-lookup"><span data-stu-id="75cc2-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="75cc2-107">此指针 `IUnknown`类型化，因此调用方通常应调用 `QueryInterface` 以获取 <xref:System._AppDomain>类型的指针。</span><span class="sxs-lookup"><span data-stu-id="75cc2-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75cc2-108">返回值</span><span class="sxs-lookup"><span data-stu-id="75cc2-108">Return Value</span></span>  
  
|<span data-ttu-id="75cc2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75cc2-109">HRESULT</span></span>|<span data-ttu-id="75cc2-110">描述</span><span class="sxs-lookup"><span data-stu-id="75cc2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75cc2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="75cc2-111">S_OK</span></span>|<span data-ttu-id="75cc2-112">操作成功。</span><span class="sxs-lookup"><span data-stu-id="75cc2-112">The operation was successful.</span></span>|  
|<span data-ttu-id="75cc2-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="75cc2-113">S_FALSE</span></span>|<span data-ttu-id="75cc2-114">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="75cc2-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="75cc2-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="75cc2-115">E_FAIL</span></span>|<span data-ttu-id="75cc2-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="75cc2-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="75cc2-117">如果某个方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="75cc2-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="75cc2-118">对任何托管 Api 的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="75cc2-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="75cc2-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="75cc2-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="75cc2-120">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="75cc2-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75cc2-121">要求</span><span class="sxs-lookup"><span data-stu-id="75cc2-121">Requirements</span></span>  
 <span data-ttu-id="75cc2-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75cc2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75cc2-123">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="75cc2-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="75cc2-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="75cc2-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75cc2-125">**.NET Framework 版本：** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="75cc2-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75cc2-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="75cc2-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="75cc2-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="75cc2-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
