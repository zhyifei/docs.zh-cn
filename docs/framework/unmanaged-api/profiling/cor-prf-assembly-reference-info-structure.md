---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO 结构
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: ac7ddeed5694ad0ae6ef3d4a11fcb1fb23755b8e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123219"
---
# <a name="cor_prf_assembly_reference_info-structure"></a><span data-ttu-id="27605-102">COR_PRF_ASSEMBLY_REFERENCE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="27605-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="27605-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="27605-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="27605-104">向公共语言运行时提供有关在执行程序集引用闭包审核时应考虑的程序集引用的信息。</span><span class="sxs-lookup"><span data-stu-id="27605-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27605-105">语法</span><span class="sxs-lookup"><span data-stu-id="27605-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="27605-106">Members</span><span class="sxs-lookup"><span data-stu-id="27605-106">Members</span></span>  
  
|<span data-ttu-id="27605-107">成员</span><span class="sxs-lookup"><span data-stu-id="27605-107">Member</span></span>|<span data-ttu-id="27605-108">描述</span><span class="sxs-lookup"><span data-stu-id="27605-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="27605-109">指向程序集的公钥或标记的指针。</span><span class="sxs-lookup"><span data-stu-id="27605-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="27605-110">公钥或标记中的字节数。</span><span class="sxs-lookup"><span data-stu-id="27605-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="27605-111">所引用的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="27605-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="27605-112">指向程序集的元数据的指针。</span><span class="sxs-lookup"><span data-stu-id="27605-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="27605-113">指向哈希二进制大对象 (BLOB) 的指针。</span><span class="sxs-lookup"><span data-stu-id="27605-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="27605-114">哈希 BLOB 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="27605-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="27605-115">程序集的标志。</span><span class="sxs-lookup"><span data-stu-id="27605-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27605-116">备注</span><span class="sxs-lookup"><span data-stu-id="27605-116">Remarks</span></span>  
 <span data-ttu-id="27605-117">当 `COR_PRF_EX_CLAUSE_INFO` 结构声明在执行程序集引用闭包审核时公共语言运行时应考虑的附加程序集引用时，该结构将由探查器进行填充。</span><span class="sxs-lookup"><span data-stu-id="27605-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="27605-118">如果探查器注册了[ICorProfilerCallback6：： GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)回调方法，则运行时将传递要加载的程序集的路径和名称以及指向[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)的指针。此方法的接口对象。</span><span class="sxs-lookup"><span data-stu-id="27605-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="27605-119">然后，探查器可以使用[ICorProfilerAssemblyReferenceProvider：： AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)方法为它计划从 ICorProfilerCallback6 中指定的程序集中引用的每个目标程序集调用一个 `COR_PRF_ASSEMBLY_REFERENCE_INFO` 对象： [GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="27605-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27605-120">要求</span><span class="sxs-lookup"><span data-stu-id="27605-120">Requirements</span></span>  
 <span data-ttu-id="27605-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27605-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27605-122">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27605-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27605-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27605-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27605-124">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27605-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27605-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="27605-125">See also</span></span>

- [<span data-ttu-id="27605-126">分析结构</span><span class="sxs-lookup"><span data-stu-id="27605-126">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
- [<span data-ttu-id="27605-127">GetAssemblyReferences 方法</span><span class="sxs-lookup"><span data-stu-id="27605-127">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="27605-128">AddAssemblyReference 方法</span><span class="sxs-lookup"><span data-stu-id="27605-128">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
