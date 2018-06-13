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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 385ccc7a63fb5eb27ae7bdda5bdcf13c750eb667
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436142"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="0655d-102">AssemblyBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="0655d-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="0655d-103">提供有关引用程序集的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="0655d-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0655d-104">语法</span><span class="sxs-lookup"><span data-stu-id="0655d-104">Syntax</span></span>  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="0655d-105">成员</span><span class="sxs-lookup"><span data-stu-id="0655d-105">Members</span></span>  
  
|<span data-ttu-id="0655d-106">成员</span><span class="sxs-lookup"><span data-stu-id="0655d-106">Member</span></span>|<span data-ttu-id="0655d-107">描述</span><span class="sxs-lookup"><span data-stu-id="0655d-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="0655d-108">唯一标识符`IStream`返回通过调用[ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)，从引用的程序集即要加载。</span><span class="sxs-lookup"><span data-stu-id="0655d-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="0655d-109">引用的程序集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0655d-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="0655d-110">之后的任何绑定策略值的应用程序引用的程序集标识符。</span><span class="sxs-lookup"><span data-stu-id="0655d-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="0655d-111">之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，用于指示哪些版本控制策略，如果有的话，应该应用于引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="0655d-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0655d-112">备注</span><span class="sxs-lookup"><span data-stu-id="0655d-112">Remarks</span></span>  
 <span data-ttu-id="0655d-113">主机提供的唯一标识符`dwAppDomainId`公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="0655d-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="0655d-114">调用了`IHostAssemblyStore::ProvideAssembly`返回时，运行时使用标识符来确定是否的内容`IStream`已映射。</span><span class="sxs-lookup"><span data-stu-id="0655d-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="0655d-115">如果是这样，则运行时将加载现有的副本，而不是无需重新映射流。</span><span class="sxs-lookup"><span data-stu-id="0655d-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="0655d-116">运行时还使用此标识符作为查找键以从返回的流调用[ihostassemblystore:: Providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)。</span><span class="sxs-lookup"><span data-stu-id="0655d-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="0655d-117">因此，标识符必须是唯一为模块请求和程序集请求。</span><span class="sxs-lookup"><span data-stu-id="0655d-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0655d-118">要求</span><span class="sxs-lookup"><span data-stu-id="0655d-118">Requirements</span></span>  
 <span data-ttu-id="0655d-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0655d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0655d-120">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="0655d-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="0655d-121">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0655d-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0655d-122">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0655d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0655d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="0655d-123">See Also</span></span>  
 [<span data-ttu-id="0655d-124">承载结构</span><span class="sxs-lookup"><span data-stu-id="0655d-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="0655d-125">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="0655d-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="0655d-126">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="0655d-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="0655d-127">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="0655d-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="0655d-128">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="0655d-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="0655d-129">ModuleBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="0655d-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
