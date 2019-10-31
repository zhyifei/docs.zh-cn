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
ms.openlocfilehash: 26de2ebf1364981d8b8f1fb38c8fa1045191114f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126628"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="e00a9-102">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="e00a9-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="e00a9-103">提供一些方法，这些方法支持宿主与公共语言运行时（CLR）与程序集之间的通信。</span><span class="sxs-lookup"><span data-stu-id="e00a9-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e00a9-104">方法</span><span class="sxs-lookup"><span data-stu-id="e00a9-104">Methods</span></span>  
  
|<span data-ttu-id="e00a9-105">方法</span><span class="sxs-lookup"><span data-stu-id="e00a9-105">Method</span></span>|<span data-ttu-id="e00a9-106">描述</span><span class="sxs-lookup"><span data-stu-id="e00a9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e00a9-107">GetBindingIdentityFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="e00a9-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="e00a9-108">获取指定文件路径处的程序集的程序集标识绑定数据。</span><span class="sxs-lookup"><span data-stu-id="e00a9-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="e00a9-109">GetBindingIdentityFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="e00a9-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="e00a9-110">获取指定流中的程序集的规范程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="e00a9-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="e00a9-111">GetCLRAssemblyReferenceList 方法</span><span class="sxs-lookup"><span data-stu-id="e00a9-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="e00a9-112">从提供的部分程序集标识列表中获取[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="e00a9-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="e00a9-113">GetProbingAssembliesFromReference 方法</span><span class="sxs-lookup"><span data-stu-id="e00a9-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="e00a9-114">获取具有指定标识的程序集所引用的程序集标识的[ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)枚举器。</span><span class="sxs-lookup"><span data-stu-id="e00a9-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="e00a9-115">GetReferencedAssembliesFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="e00a9-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="e00a9-116">获取一个[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)实例，该实例包含程序集在指定文件路径处引用的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="e00a9-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="e00a9-117">GetReferencedAssembliesFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="e00a9-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="e00a9-118">获取一个指向 `ICLRReferenceAssemblyEnum` 对象的指针，该对象包含指定流中的程序集引用的程序集的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="e00a9-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="e00a9-119">IsStronglyNamed 方法</span><span class="sxs-lookup"><span data-stu-id="e00a9-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="e00a9-120">获取一个值，该值指示指定的程序集是否具有强名称。</span><span class="sxs-lookup"><span data-stu-id="e00a9-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e00a9-121">备注</span><span class="sxs-lookup"><span data-stu-id="e00a9-121">Remarks</span></span>  
 <span data-ttu-id="e00a9-122">使用 `ICLRAssemblyIdentityManager` 获取 `ICLRAssemblyReferenceList` 的实例并枚举程序集标识。</span><span class="sxs-lookup"><span data-stu-id="e00a9-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e00a9-123">要求</span><span class="sxs-lookup"><span data-stu-id="e00a9-123">Requirements</span></span>  
 <span data-ttu-id="e00a9-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e00a9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e00a9-125">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e00a9-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e00a9-126">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e00a9-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e00a9-127">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e00a9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e00a9-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e00a9-128">See also</span></span>

- [<span data-ttu-id="e00a9-129">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="e00a9-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e00a9-130">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="e00a9-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="e00a9-131">承载接口</span><span class="sxs-lookup"><span data-stu-id="e00a9-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
