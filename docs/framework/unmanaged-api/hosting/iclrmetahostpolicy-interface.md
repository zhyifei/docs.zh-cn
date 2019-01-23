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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46576552db6e3c9aa06646b260e74cb4b7890d9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559224"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="c4b24-102">ICLRMetaHostPolicy 接口</span><span class="sxs-lookup"><span data-stu-id="c4b24-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="c4b24-103">提供了[GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法，它将指针返回到策略条件的一个公共语言运行时 (CLR) 接口，托管程序集、 版本和配置文件。</span><span class="sxs-lookup"><span data-stu-id="c4b24-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4b24-104">方法</span><span class="sxs-lookup"><span data-stu-id="c4b24-104">Methods</span></span>  
  
|<span data-ttu-id="c4b24-105">方法</span><span class="sxs-lookup"><span data-stu-id="c4b24-105">Method</span></span>|<span data-ttu-id="c4b24-106">描述</span><span class="sxs-lookup"><span data-stu-id="c4b24-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4b24-107">GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="c4b24-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="c4b24-108">提供首选的 CLR 接口基于策略条件，请在托管程序集、 版本和配置文件。</span><span class="sxs-lookup"><span data-stu-id="c4b24-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4b24-109">备注</span><span class="sxs-lookup"><span data-stu-id="c4b24-109">Remarks</span></span>  
 <span data-ttu-id="c4b24-110">您可以通过调用获取对此接口的引用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数，下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="c4b24-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="c4b24-111">此接口不会真的不加载或激活 CLR，但只需返回的首选的 CLR 版本基于在安装和加载的可用版本。</span><span class="sxs-lookup"><span data-stu-id="c4b24-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="c4b24-112">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]托管 API 合并了各种策略，以便具有特定需求的主机可能会使用基本功能，而不会产生意外的损失。</span><span class="sxs-lookup"><span data-stu-id="c4b24-112">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="c4b24-113">例如，许多 MSCorEE.dll 导出将绑定到特定的 CLR，虽然一种方法可能会以逻辑方式需要它。</span><span class="sxs-lookup"><span data-stu-id="c4b24-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="c4b24-114">[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)枚举提供主机的大部分常见的绑定策略。</span><span class="sxs-lookup"><span data-stu-id="c4b24-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4b24-115">要求</span><span class="sxs-lookup"><span data-stu-id="c4b24-115">Requirements</span></span>  
 <span data-ttu-id="c4b24-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b24-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b24-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c4b24-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c4b24-118">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c4b24-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4b24-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b24-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b24-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b24-120">See also</span></span>
- [<span data-ttu-id="c4b24-121">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="c4b24-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="c4b24-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="c4b24-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c4b24-123">承载</span><span class="sxs-lookup"><span data-stu-id="c4b24-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
