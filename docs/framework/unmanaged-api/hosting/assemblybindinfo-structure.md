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
ms.openlocfilehash: 0247f356bfc9f354edc420ea5460da02b17ab116
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561135"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="3184c-102">AssemblyBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="3184c-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="3184c-103">提供有关引用程序集的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="3184c-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3184c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3184c-104">Syntax</span></span>  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="3184c-105">成员</span><span class="sxs-lookup"><span data-stu-id="3184c-105">Members</span></span>  
  
|<span data-ttu-id="3184c-106">成员</span><span class="sxs-lookup"><span data-stu-id="3184c-106">Member</span></span>|<span data-ttu-id="3184c-107">描述</span><span class="sxs-lookup"><span data-stu-id="3184c-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="3184c-108">唯一标识符`IStream`返回通过调用[ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)，从该引用的程序集将被加载。</span><span class="sxs-lookup"><span data-stu-id="3184c-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="3184c-109">引用的程序集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3184c-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="3184c-110">引用的程序集之后的任何绑定策略值的应用程序标识符。</span><span class="sxs-lookup"><span data-stu-id="3184c-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="3184c-111">之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，用于指示哪些版本控制策略，如果有的话，应将应用于引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="3184c-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3184c-112">备注</span><span class="sxs-lookup"><span data-stu-id="3184c-112">Remarks</span></span>  
 <span data-ttu-id="3184c-113">主机提供的唯一标识符`dwAppDomainId`到公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="3184c-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="3184c-114">在调用`IHostAssemblyStore::ProvideAssembly`返回时，运行时使用标识符来确定是否的内容`IStream`已映射。</span><span class="sxs-lookup"><span data-stu-id="3184c-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="3184c-115">如果是这样，在运行时加载的现有副本，而不是无需重新映射该流。</span><span class="sxs-lookup"><span data-stu-id="3184c-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="3184c-116">运行时也使用此标识符作为查找键从流返回到调用[ihostassemblystore:: Providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3184c-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="3184c-117">因此，标识符必须是唯一的模块请求和程序集发出请求。</span><span class="sxs-lookup"><span data-stu-id="3184c-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3184c-118">要求</span><span class="sxs-lookup"><span data-stu-id="3184c-118">Requirements</span></span>  
 <span data-ttu-id="3184c-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3184c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3184c-120">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="3184c-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="3184c-121">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3184c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3184c-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3184c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3184c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="3184c-123">See also</span></span>
- [<span data-ttu-id="3184c-124">承载结构</span><span class="sxs-lookup"><span data-stu-id="3184c-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="3184c-125">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="3184c-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="3184c-126">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="3184c-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="3184c-127">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="3184c-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="3184c-128">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="3184c-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="3184c-129">ModuleBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="3184c-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
