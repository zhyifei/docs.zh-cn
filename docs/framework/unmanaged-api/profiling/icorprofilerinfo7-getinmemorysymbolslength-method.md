---
title: 'ICorProfilerInfo7:: GetInMemorySymbolsLength 方法'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157b0e215f8afa58cccb3d54a65baa9c307ba966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955424"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="ae1e6-102">ICorProfilerInfo7:: GetInMemorySymbolsLength 方法</span><span class="sxs-lookup"><span data-stu-id="ae1e6-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="ae1e6-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="ae1e6-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="ae1e6-104">返回内存中符号流的长度。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae1e6-105">语法</span><span class="sxs-lookup"><span data-stu-id="ae1e6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae1e6-106">参数</span><span class="sxs-lookup"><span data-stu-id="ae1e6-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ae1e6-107">中包含内存中流的模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="ae1e6-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="ae1e6-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="ae1e6-109">弄一个指向`DWORD`值的指针, 当该方法返回时, 将包含流的长度 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae1e6-110">返回值</span><span class="sxs-lookup"><span data-stu-id="ae1e6-110">Return Value</span></span>  
 <span data-ttu-id="ae1e6-111">如果可以确定`S_OK`内存流的长度 (即使它为零 (0)), 则方法将返回。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="ae1e6-112">如果该方法`CORPROF_E_MODULE_IS_DYNAMIC`是使用<xref:System.Reflection.Emit?displayProperty=nameWithType>创建的, 则该方法返回。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae1e6-113">备注</span><span class="sxs-lookup"><span data-stu-id="ae1e6-113">Remarks</span></span>  
 <span data-ttu-id="ae1e6-114">如果模块有内存中符号, 则流的长度将被置于中`pCountSymbolBytes`。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="ae1e6-115">如果模块没有内存中符号, `*pCountSymbolBytes = 0`则为。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae1e6-116">当前实现不支持反射。发出。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="ae1e6-117">如果该模块是使用反射创建的, 则该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae1e6-118">要求</span><span class="sxs-lookup"><span data-stu-id="ae1e6-118">Requirements</span></span>  
 <span data-ttu-id="ae1e6-119">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae1e6-120">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="ae1e6-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae1e6-121">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae1e6-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae1e6-122">**.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae1e6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae1e6-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae1e6-123">See also</span></span>

- [<span data-ttu-id="ae1e6-124">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="ae1e6-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
