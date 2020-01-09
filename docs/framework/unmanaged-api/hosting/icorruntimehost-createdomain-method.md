---
title: ICorRuntimeHost::CreateDomain 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
ms.openlocfilehash: 7c3e37fdb8a5afc973c913b1cfa56ab2e9f4fa52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127734"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="06b7c-102">ICorRuntimeHost::CreateDomain 方法</span><span class="sxs-lookup"><span data-stu-id="06b7c-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="06b7c-103">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="06b7c-103">Creates an application domain.</span></span> <span data-ttu-id="06b7c-104">调用方将 <xref:System._AppDomain> 类型的接口指针接收到 <xref:System.AppDomain?displayProperty=nameWithType>类型的实例。</span><span class="sxs-lookup"><span data-stu-id="06b7c-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b7c-105">语法</span><span class="sxs-lookup"><span data-stu-id="06b7c-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06b7c-106">参数</span><span class="sxs-lookup"><span data-stu-id="06b7c-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="06b7c-107">中用于给域指定友好名称的可选参数。</span><span class="sxs-lookup"><span data-stu-id="06b7c-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="06b7c-108">此友好名称可在用户界面（例如调试器）中显示，以标识域。</span><span class="sxs-lookup"><span data-stu-id="06b7c-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="06b7c-109">中指向 `IIdentity` 实例的可选指针数组，这些实例表示通过安全策略映射以建立权限集的证据。</span><span class="sxs-lookup"><span data-stu-id="06b7c-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="06b7c-110">可以通过调用[CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)方法来获取 `IIdentity` 的对象。</span><span class="sxs-lookup"><span data-stu-id="06b7c-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="06b7c-111">弄类型的接口指针 <xref:System._AppDomain> 到可用于进一步控制域的 <xref:System.AppDomain?displayProperty=nameWithType> 的实例。</span><span class="sxs-lookup"><span data-stu-id="06b7c-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06b7c-112">返回值</span><span class="sxs-lookup"><span data-stu-id="06b7c-112">Return Value</span></span>  
  
|<span data-ttu-id="06b7c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06b7c-113">HRESULT</span></span>|<span data-ttu-id="06b7c-114">描述</span><span class="sxs-lookup"><span data-stu-id="06b7c-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06b7c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="06b7c-115">S_OK</span></span>|<span data-ttu-id="06b7c-116">操作成功。</span><span class="sxs-lookup"><span data-stu-id="06b7c-116">The operation was successful.</span></span>|  
|<span data-ttu-id="06b7c-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="06b7c-117">S_FALSE</span></span>|<span data-ttu-id="06b7c-118">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="06b7c-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="06b7c-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06b7c-119">E_FAIL</span></span>|<span data-ttu-id="06b7c-120">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="06b7c-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="06b7c-121">如果某个方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="06b7c-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="06b7c-122">对任何托管 Api 的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="06b7c-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="06b7c-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="06b7c-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="06b7c-124">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="06b7c-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06b7c-125">要求</span><span class="sxs-lookup"><span data-stu-id="06b7c-125">Requirements</span></span>  
 <span data-ttu-id="06b7c-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06b7c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06b7c-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="06b7c-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06b7c-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="06b7c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06b7c-129">**.NET Framework 版本：** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="06b7c-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b7c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="06b7c-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="06b7c-131">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="06b7c-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
