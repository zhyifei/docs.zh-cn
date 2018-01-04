---
title: "ICLRMetaHostPolicy 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHostPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHostPolicy
helpviewer_keywords: ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cd9b8d6aef2289833a0bd192b838e6f70ea8c0ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="80ae4-102">ICLRMetaHostPolicy 接口</span><span class="sxs-lookup"><span data-stu-id="80ae4-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="80ae4-103">提供[GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法，将指针返回到基于策略条件的公共语言运行时 (CLR) 接口，托管程序集、 版本和配置文件。</span><span class="sxs-lookup"><span data-stu-id="80ae4-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80ae4-104">方法</span><span class="sxs-lookup"><span data-stu-id="80ae4-104">Methods</span></span>  
  
|<span data-ttu-id="80ae4-105">方法</span><span class="sxs-lookup"><span data-stu-id="80ae4-105">Method</span></span>|<span data-ttu-id="80ae4-106">描述</span><span class="sxs-lookup"><span data-stu-id="80ae4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80ae4-107">GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="80ae4-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="80ae4-108">提供了首选的 CLR 接口基于策略条件、 托管程序集、 版本和配置文件。</span><span class="sxs-lookup"><span data-stu-id="80ae4-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80ae4-109">备注</span><span class="sxs-lookup"><span data-stu-id="80ae4-109">Remarks</span></span>  
 <span data-ttu-id="80ae4-110">你可以通过调用获取对此接口的引用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="80ae4-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="80ae4-111">此接口不实际上不会加载或激活 CLR，但只需返回的首选的 CLR 版本基于安装或未加载的可用版本。</span><span class="sxs-lookup"><span data-stu-id="80ae4-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="80ae4-112">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]托管 API 将合并策略，以便的特定需求的主机可以使用基本功能，而不会产生意外的损失。</span><span class="sxs-lookup"><span data-stu-id="80ae4-112">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="80ae4-113">例如，许多 MSCorEE.dll 导出将绑定到特定的 CLR，虽然方法可能逻辑上需要它。</span><span class="sxs-lookup"><span data-stu-id="80ae4-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="80ae4-114">[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)枚举提供了所共有的大部分主机的绑定策略。</span><span class="sxs-lookup"><span data-stu-id="80ae4-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80ae4-115">惠?</span><span class="sxs-lookup"><span data-stu-id="80ae4-115">Requirements</span></span>  
 <span data-ttu-id="80ae4-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80ae4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ae4-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="80ae4-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="80ae4-118">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="80ae4-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80ae4-119">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80ae4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ae4-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="80ae4-120">See Also</span></span>  
 [<span data-ttu-id="80ae4-121">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="80ae4-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="80ae4-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="80ae4-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="80ae4-123">承载</span><span class="sxs-lookup"><span data-stu-id="80ae4-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
