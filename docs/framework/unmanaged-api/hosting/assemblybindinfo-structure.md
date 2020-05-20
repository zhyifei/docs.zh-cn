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
ms.openlocfilehash: 615637813b08629aaea74b23fa2737f52d61bafb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616913"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="5185c-102">AssemblyBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="5185c-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="5185c-103">提供有关所引用程序集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5185c-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5185c-104">语法</span><span class="sxs-lookup"><span data-stu-id="5185c-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="5185c-105">成员</span><span class="sxs-lookup"><span data-stu-id="5185c-105">Members</span></span>  
  
|<span data-ttu-id="5185c-106">成员</span><span class="sxs-lookup"><span data-stu-id="5185c-106">Member</span></span>|<span data-ttu-id="5185c-107">描述</span><span class="sxs-lookup"><span data-stu-id="5185c-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="5185c-108">`IStream`通过调用[IHostAssemblyStore：:P rovideassembly](ihostassemblystore-provideassembly-method.md)返回的的唯一标识符，将从中加载所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="5185c-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="5185c-109">所引用程序集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5185c-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="5185c-110">在应用任何绑定策略值之后引用的程序集的标识符。</span><span class="sxs-lookup"><span data-stu-id="5185c-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="5185c-111">[EPolicyAction](epolicyaction-enumeration.md)值之一，指示应将哪些版本控制策略应用于所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="5185c-111">One of the [EPolicyAction](epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5185c-112">备注</span><span class="sxs-lookup"><span data-stu-id="5185c-112">Remarks</span></span>  
 <span data-ttu-id="5185c-113">宿主 `dwAppDomainId` 向公共语言运行时（CLR）提供唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5185c-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="5185c-114">在对的调用 `IHostAssemblyStore::ProvideAssembly` 返回后，运行时将使用标识符来确定是否已映射的内容 `IStream` 。</span><span class="sxs-lookup"><span data-stu-id="5185c-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="5185c-115">如果是这样，则运行时加载现有副本，而不是重新映射流。</span><span class="sxs-lookup"><span data-stu-id="5185c-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="5185c-116">运行时还会将此标识符用作从对[IHostAssemblyStore：:P rovidemodule](ihostassemblystore-providemodule-method.md)的调用返回的流的查找密钥。</span><span class="sxs-lookup"><span data-stu-id="5185c-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="5185c-117">因此，对于模块请求和程序集请求，标识符必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="5185c-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5185c-118">要求</span><span class="sxs-lookup"><span data-stu-id="5185c-118">Requirements</span></span>  
 <span data-ttu-id="5185c-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5185c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5185c-120">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5185c-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5185c-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5185c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5185c-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5185c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5185c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5185c-123">See also</span></span>

- [<span data-ttu-id="5185c-124">承载结构</span><span class="sxs-lookup"><span data-stu-id="5185c-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="5185c-125">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="5185c-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="5185c-126">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="5185c-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="5185c-127">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="5185c-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="5185c-128">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="5185c-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="5185c-129">ModuleBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="5185c-129">ModuleBindInfo Structure</span></span>](modulebindinfo-structure.md)
