---
title: "ICorDebugSymbolProvider 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63823c535ad4d036dd5d539c8fe5381d350ccbe5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="c07a5-102">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="c07a5-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="c07a5-103">提供可用于检索调试符号信息的方法。</span><span class="sxs-lookup"><span data-stu-id="c07a5-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c07a5-104">方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-104">Methods</span></span>  
  
|<span data-ttu-id="c07a5-105">方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-105">Method</span></span>|<span data-ttu-id="c07a5-106">描述</span><span class="sxs-lookup"><span data-stu-id="c07a5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c07a5-107">GetAssemblyImageBytes 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-107">GetAssemblyImageBytes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="c07a5-108">给定合并程序集的相对虚拟地址 (RVA)，读取合并程序集中的数据。</span><span class="sxs-lookup"><span data-stu-id="c07a5-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="c07a5-109">GetAssemblyImageMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-109">GetAssemblyImageMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="c07a5-110">返回合并程序集中的元数据。</span><span class="sxs-lookup"><span data-stu-id="c07a5-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="c07a5-111">GetCodeRange 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-111">GetCodeRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="c07a5-112">给定方法的相对虚拟地址 (RVA)，获取该方法的起始地址和大小。</span><span class="sxs-lookup"><span data-stu-id="c07a5-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="c07a5-113">GetInstanceFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-113">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="c07a5-114">获取与 Typespec 签名相对应的实例字段符号。</span><span class="sxs-lookup"><span data-stu-id="c07a5-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="c07a5-115">GetMergedAssemblyRecords 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-115">GetMergedAssemblyRecords Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="c07a5-116">获取所有合并程序集的符号记录。</span><span class="sxs-lookup"><span data-stu-id="c07a5-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="c07a5-117">GetMethodLocalSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-117">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="c07a5-118">给定方法的相对虚拟地址 (RVA)，获取该方法的本地符号。</span><span class="sxs-lookup"><span data-stu-id="c07a5-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="c07a5-119">GetMethodParameterSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-119">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="c07a5-120">给定方法的相对虚拟地址 (RVA) 后，获取该方法的参数符号。</span><span class="sxs-lookup"><span data-stu-id="c07a5-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="c07a5-121">GetMethodProps 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="c07a5-122">给定方法的相对虚拟地址 (RVA)，返回有关该方法属性的信息，例如该方法的元数据标记及其泛型参数信息。</span><span class="sxs-lookup"><span data-stu-id="c07a5-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="c07a5-123">GetObjectSize 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-123">GetObjectSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="c07a5-124">基于对象的 Typespec 签名返回对象的大小。</span><span class="sxs-lookup"><span data-stu-id="c07a5-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="c07a5-125">GetStaticFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-125">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="c07a5-126">获取与 Typespec 签名相对应的静态字段符号。</span><span class="sxs-lookup"><span data-stu-id="c07a5-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="c07a5-127">GetTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="c07a5-127">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="c07a5-128">给定 vtable 中的相对虚拟地址 (RVA)，返回类型的属性信息（例如其泛型参数的签名数量）。</span><span class="sxs-lookup"><span data-stu-id="c07a5-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c07a5-129">备注</span><span class="sxs-lookup"><span data-stu-id="c07a5-129">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c07a5-130">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="c07a5-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="c07a5-131">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="c07a5-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c07a5-132">惠?</span><span class="sxs-lookup"><span data-stu-id="c07a5-132">Requirements</span></span>  
 <span data-ttu-id="c07a5-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c07a5-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c07a5-134">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c07a5-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c07a5-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c07a5-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c07a5-136">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c07a5-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c07a5-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="c07a5-137">See Also</span></span>  
 [<span data-ttu-id="c07a5-138">调试接口</span><span class="sxs-lookup"><span data-stu-id="c07a5-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c07a5-139">调试</span><span class="sxs-lookup"><span data-stu-id="c07a5-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
