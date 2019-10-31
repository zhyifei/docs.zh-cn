---
title: ICLRMetaHostPolicy 接口
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 277c13895374116eb67f6515f45df638f61b0453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140853"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="b104b-102">ICLRMetaHostPolicy 接口</span><span class="sxs-lookup"><span data-stu-id="b104b-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="b104b-103">提供[GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法，该方法根据策略条件、托管程序集、版本和配置文件返回指向公共语言运行时（CLR）接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b104b-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b104b-104">方法</span><span class="sxs-lookup"><span data-stu-id="b104b-104">Methods</span></span>  
  
|<span data-ttu-id="b104b-105">方法</span><span class="sxs-lookup"><span data-stu-id="b104b-105">Method</span></span>|<span data-ttu-id="b104b-106">描述</span><span class="sxs-lookup"><span data-stu-id="b104b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b104b-107">GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="b104b-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="b104b-108">提供基于策略标准、托管程序集、版本和配置文件的首选 CLR 接口。</span><span class="sxs-lookup"><span data-stu-id="b104b-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b104b-109">备注</span><span class="sxs-lookup"><span data-stu-id="b104b-109">Remarks</span></span>  
 <span data-ttu-id="b104b-110">可以通过调用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数获取对此接口的引用，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="b104b-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="b104b-111">此接口实际上不会加载或激活 CLR，只是根据安装或加载的可用版本返回首选 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="b104b-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="b104b-112">.NET Framework 4 托管 API 合并了策略，因此具有特定需求的主机可以使用基本功能，而不会产生意外的处罚。</span><span class="sxs-lookup"><span data-stu-id="b104b-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="b104b-113">例如，许多 Mscoree.dll 导出将绑定到特定的 CLR，不过，方法可能不会在逻辑上要求它。</span><span class="sxs-lookup"><span data-stu-id="b104b-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="b104b-114">[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)枚举提供大部分主机所共有的绑定策略。</span><span class="sxs-lookup"><span data-stu-id="b104b-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b104b-115">要求</span><span class="sxs-lookup"><span data-stu-id="b104b-115">Requirements</span></span>  
 <span data-ttu-id="b104b-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b104b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b104b-117">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="b104b-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b104b-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b104b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b104b-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b104b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b104b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b104b-120">See also</span></span>

- [<span data-ttu-id="b104b-121">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="b104b-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="b104b-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="b104b-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b104b-123">承载</span><span class="sxs-lookup"><span data-stu-id="b104b-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
