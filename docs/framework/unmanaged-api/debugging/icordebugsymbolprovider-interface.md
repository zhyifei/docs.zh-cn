---
title: ICorDebugSymbolProvider 接口
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc33018f68f9634a29e2f5c52123a0215b446de7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228960"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="a8d6e-102">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="a8d6e-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="a8d6e-103">提供可用于检索调试符号信息的方法。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8d6e-104">方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-104">Methods</span></span>  
  
|<span data-ttu-id="a8d6e-105">方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-105">Method</span></span>|<span data-ttu-id="a8d6e-106">描述</span><span class="sxs-lookup"><span data-stu-id="a8d6e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8d6e-107">GetAssemblyImageBytes 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-107">GetAssemblyImageBytes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="a8d6e-108">给定合并程序集的相对虚拟地址 (RVA)，读取合并程序集中的数据。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="a8d6e-109">GetAssemblyImageMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-109">GetAssemblyImageMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="a8d6e-110">返回合并程序集中的元数据。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="a8d6e-111">GetCodeRange 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-111">GetCodeRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="a8d6e-112">给定方法的相对虚拟地址 (RVA)，获取该方法的起始地址和大小。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="a8d6e-113">GetInstanceFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-113">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="a8d6e-114">获取与 Typespec 签名相对应的实例字段符号。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="a8d6e-115">GetMergedAssemblyRecords 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-115">GetMergedAssemblyRecords Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="a8d6e-116">获取所有合并程序集的符号记录。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="a8d6e-117">GetMethodLocalSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-117">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="a8d6e-118">给定方法的相对虚拟地址 (RVA)，获取该方法的本地符号。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="a8d6e-119">GetMethodParameterSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-119">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="a8d6e-120">给定方法的相对虚拟地址 (RVA) 后，获取该方法的参数符号。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="a8d6e-121">GetMethodProps 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="a8d6e-122">给定方法的相对虚拟地址 (RVA)，返回有关该方法属性的信息，例如该方法的元数据标记及其泛型参数信息。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="a8d6e-123">GetObjectSize 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-123">GetObjectSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="a8d6e-124">基于对象的 TypeSpec 签名返回对象的大小。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="a8d6e-125">GetStaticFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-125">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="a8d6e-126">获取与 Typespec 签名相对应的静态字段符号。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="a8d6e-127">GetTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="a8d6e-127">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="a8d6e-128">给定 vtable 中的相对虚拟地址 (RVA)，返回类型的属性信息（例如其泛型参数的签名数量）。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8d6e-129">备注</span><span class="sxs-lookup"><span data-stu-id="a8d6e-129">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8d6e-130">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a8d6e-131">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8d6e-132">要求</span><span class="sxs-lookup"><span data-stu-id="a8d6e-132">Requirements</span></span>  
 <span data-ttu-id="a8d6e-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8d6e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8d6e-134">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8d6e-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8d6e-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8d6e-135">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a8d6e-136">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a8d6e-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a8d6e-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8d6e-137">See also</span></span>

- [<span data-ttu-id="a8d6e-138">调试接口</span><span class="sxs-lookup"><span data-stu-id="a8d6e-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a8d6e-139">调试</span><span class="sxs-lookup"><span data-stu-id="a8d6e-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
