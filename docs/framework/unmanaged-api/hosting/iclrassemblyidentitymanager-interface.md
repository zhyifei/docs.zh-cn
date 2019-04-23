---
title: ICLRAssemblyIdentityManager 接口
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b209e568b1e65ed785155d045cd48d1248672da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209796"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="d9199-102">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="d9199-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="d9199-103">提供支持在主机和公共语言运行时 (CLR) 有关程序集之间的通信的方法。</span><span class="sxs-lookup"><span data-stu-id="d9199-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9199-104">方法</span><span class="sxs-lookup"><span data-stu-id="d9199-104">Methods</span></span>  
  
|<span data-ttu-id="d9199-105">方法</span><span class="sxs-lookup"><span data-stu-id="d9199-105">Method</span></span>|<span data-ttu-id="d9199-106">描述</span><span class="sxs-lookup"><span data-stu-id="d9199-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9199-107">GetBindingIdentityFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="d9199-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="d9199-108">获取数据绑定的程序集在指定的文件路径的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="d9199-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="d9199-109">GetBindingIdentityFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="d9199-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="d9199-110">获取指定的流中的程序集的规范的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="d9199-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="d9199-111">GetCLRAssemblyReferenceList 方法</span><span class="sxs-lookup"><span data-stu-id="d9199-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="d9199-112">获取[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)从提供的列表的部分程序集标识的实例。</span><span class="sxs-lookup"><span data-stu-id="d9199-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="d9199-113">GetProbingAssembliesFromReference 方法</span><span class="sxs-lookup"><span data-stu-id="d9199-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="d9199-114">获取[ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)具有指定标识该程序集引用的程序集标识的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d9199-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="d9199-115">GetReferencedAssembliesFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="d9199-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="d9199-116">获取[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)实例，其中包含指定的文件路径在程序集引用的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="d9199-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="d9199-117">GetReferencedAssembliesFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="d9199-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="d9199-118">获取一个指向`ICLRReferenceAssemblyEnum`对象，其中包含由指定的流中的程序集引用的程序集的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="d9199-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="d9199-119">IsStronglyNamed 方法</span><span class="sxs-lookup"><span data-stu-id="d9199-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="d9199-120">获取一个值，该值指示是否指定的程序集具有强名称。</span><span class="sxs-lookup"><span data-stu-id="d9199-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9199-121">备注</span><span class="sxs-lookup"><span data-stu-id="d9199-121">Remarks</span></span>  
 <span data-ttu-id="d9199-122">使用`ICLRAssemblyIdentityManager`获取的实例`ICLRAssemblyReferenceList`和要枚举的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="d9199-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9199-123">要求</span><span class="sxs-lookup"><span data-stu-id="d9199-123">Requirements</span></span>  
 <span data-ttu-id="d9199-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9199-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9199-125">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d9199-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9199-126">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d9199-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9199-127">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9199-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9199-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9199-128">See also</span></span>

- [<span data-ttu-id="d9199-129">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="d9199-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d9199-130">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="d9199-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="d9199-131">承载接口</span><span class="sxs-lookup"><span data-stu-id="d9199-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
