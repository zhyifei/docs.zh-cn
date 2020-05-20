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
ms.openlocfilehash: f06c8228d5eb850c0d5ff94d12be03d7fb75023b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615912"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="ff7c4-102">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="ff7c4-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="ff7c4-103">提供一些方法，这些方法支持宿主与公共语言运行时（CLR）与程序集之间的通信。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff7c4-104">方法</span><span class="sxs-lookup"><span data-stu-id="ff7c4-104">Methods</span></span>  
  
|<span data-ttu-id="ff7c4-105">方法</span><span class="sxs-lookup"><span data-stu-id="ff7c4-105">Method</span></span>|<span data-ttu-id="ff7c4-106">说明</span><span class="sxs-lookup"><span data-stu-id="ff7c4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff7c4-107">GetBindingIdentityFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="ff7c4-107">GetBindingIdentityFromFile Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="ff7c4-108">获取指定文件路径处的程序集的程序集标识绑定数据。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="ff7c4-109">GetBindingIdentityFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="ff7c4-109">GetBindingIdentityFromStream Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="ff7c4-110">获取指定流中的程序集的规范程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="ff7c4-111">GetCLRAssemblyReferenceList 方法</span><span class="sxs-lookup"><span data-stu-id="ff7c4-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="ff7c4-112">从提供的部分程序集标识列表中获取[ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-112">Gets an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="ff7c4-113">GetProbingAssembliesFromReference 方法</span><span class="sxs-lookup"><span data-stu-id="ff7c4-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="ff7c4-114">获取具有指定标识的程序集所引用的程序集标识的[ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)枚举器。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-114">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="ff7c4-115">GetReferencedAssembliesFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="ff7c4-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="ff7c4-116">获取一个[ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md)实例，该实例包含程序集在指定文件路径处引用的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-116">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="ff7c4-117">GetReferencedAssembliesFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="ff7c4-117">GetReferencedAssembliesFromStream Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="ff7c4-118">获取一个指向 `ICLRReferenceAssemblyEnum` 对象的指针，该对象包含指定流中的程序集所引用的程序集的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="ff7c4-119">IsStronglyNamed 方法</span><span class="sxs-lookup"><span data-stu-id="ff7c4-119">IsStronglyNamed Method</span></span>](iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="ff7c4-120">获取一个值，该值指示指定的程序集是否具有强名称。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff7c4-121">备注</span><span class="sxs-lookup"><span data-stu-id="ff7c4-121">Remarks</span></span>  
 <span data-ttu-id="ff7c4-122">用于 `ICLRAssemblyIdentityManager` 获取的实例 `ICLRAssemblyReferenceList` 并枚举程序集标识。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff7c4-123">要求</span><span class="sxs-lookup"><span data-stu-id="ff7c4-123">Requirements</span></span>  
 <span data-ttu-id="ff7c4-124">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff7c4-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff7c4-125">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ff7c4-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff7c4-126">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ff7c4-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff7c4-127">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff7c4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff7c4-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff7c4-128">See also</span></span>

- [<span data-ttu-id="ff7c4-129">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="ff7c4-129">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ff7c4-130">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="ff7c4-130">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="ff7c4-131">承载接口</span><span class="sxs-lookup"><span data-stu-id="ff7c4-131">Hosting Interfaces</span></span>](hosting-interfaces.md)
