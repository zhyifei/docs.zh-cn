---
title: AssemblyBindInfo 结构
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
ms.openlocfilehash: 8764a3d665c997460419561eb168f92ca769c30c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192116"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="f76bd-102">AssemblyBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="f76bd-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="f76bd-103">提供有关所引用程序集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f76bd-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f76bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="f76bd-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="f76bd-105">Members</span><span class="sxs-lookup"><span data-stu-id="f76bd-105">Members</span></span>  
  
|<span data-ttu-id="f76bd-106">成员</span><span class="sxs-lookup"><span data-stu-id="f76bd-106">Member</span></span>|<span data-ttu-id="f76bd-107">描述</span><span class="sxs-lookup"><span data-stu-id="f76bd-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="f76bd-108">调用[IHostAssemblyStore：:P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)的调用所返回的 `IStream` 的唯一标识符，将从中加载所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="f76bd-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="f76bd-109">所引用程序集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f76bd-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="f76bd-110">在应用任何绑定策略值之后引用的程序集的标识符。</span><span class="sxs-lookup"><span data-stu-id="f76bd-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="f76bd-111">[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值之一，指示应将哪些版本控制策略应用于所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="f76bd-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f76bd-112">备注</span><span class="sxs-lookup"><span data-stu-id="f76bd-112">Remarks</span></span>  
 <span data-ttu-id="f76bd-113">宿主向公共语言运行时（CLR） `dwAppDomainId` 提供唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f76bd-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="f76bd-114">在对 `IHostAssemblyStore::ProvideAssembly` 的调用返回后，运行时将使用标识符来确定是否已映射 `IStream` 的内容。</span><span class="sxs-lookup"><span data-stu-id="f76bd-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="f76bd-115">如果是这样，则运行时加载现有副本，而不是重新映射流。</span><span class="sxs-lookup"><span data-stu-id="f76bd-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="f76bd-116">运行时还会将此标识符用作从对[IHostAssemblyStore：:P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)的调用返回的流的查找密钥。</span><span class="sxs-lookup"><span data-stu-id="f76bd-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="f76bd-117">因此，对于模块请求和程序集请求，标识符必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f76bd-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f76bd-118">要求</span><span class="sxs-lookup"><span data-stu-id="f76bd-118">Requirements</span></span>  
 <span data-ttu-id="f76bd-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f76bd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f76bd-120">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f76bd-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f76bd-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f76bd-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f76bd-122">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f76bd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f76bd-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f76bd-123">See also</span></span>

- [<span data-ttu-id="f76bd-124">承载结构</span><span class="sxs-lookup"><span data-stu-id="f76bd-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="f76bd-125">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="f76bd-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f76bd-126">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="f76bd-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f76bd-127">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="f76bd-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="f76bd-128">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="f76bd-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="f76bd-129">ModuleBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="f76bd-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
