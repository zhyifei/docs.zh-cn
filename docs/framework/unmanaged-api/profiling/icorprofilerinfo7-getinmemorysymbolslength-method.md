---
title: ICorProfilerInfo7::GetInMemorySymbolsLength 方法
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
ms.openlocfilehash: 5e662270fc8db3fb85e058e8d4f3346f58f79bb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457956"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="339bc-102">ICorProfilerInfo7::GetInMemorySymbolsLength 方法</span><span class="sxs-lookup"><span data-stu-id="339bc-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="339bc-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="339bc-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="339bc-104">返回的内存中的符号流的长度。</span><span class="sxs-lookup"><span data-stu-id="339bc-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="339bc-105">语法</span><span class="sxs-lookup"><span data-stu-id="339bc-105">Syntax</span></span>  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="339bc-106">参数</span><span class="sxs-lookup"><span data-stu-id="339bc-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="339bc-107">[in]包含内存中流的模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="339bc-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="339bc-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="339bc-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="339bc-109">[out]指向的指针`DWORD`，方法返回时，包含值的以字节为单位的流长度。</span><span class="sxs-lookup"><span data-stu-id="339bc-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="339bc-110">返回值</span><span class="sxs-lookup"><span data-stu-id="339bc-110">Return Value</span></span>  
 <span data-ttu-id="339bc-111">该方法返回`S_OK`如果内存流的长度就可以确定，即使它是零 (0)。</span><span class="sxs-lookup"><span data-stu-id="339bc-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="339bc-112">该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`如果方法使用创建<xref:System.Reflection.Emit?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="339bc-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="339bc-113">备注</span><span class="sxs-lookup"><span data-stu-id="339bc-113">Remarks</span></span>  
 <span data-ttu-id="339bc-114">如果该模块具有内存中的符号，将流的长度放置在`pCountSymbolBytes`。</span><span class="sxs-lookup"><span data-stu-id="339bc-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="339bc-115">如果该模块不具有内存中符号`*pCountSymbolBytes = 0`。</span><span class="sxs-lookup"><span data-stu-id="339bc-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="339bc-116">当前实现不支持 Reflection.Emit。</span><span class="sxs-lookup"><span data-stu-id="339bc-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="339bc-117">如果通过使用 Reflection.Emit 创建模块，该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`。</span><span class="sxs-lookup"><span data-stu-id="339bc-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="339bc-118">要求</span><span class="sxs-lookup"><span data-stu-id="339bc-118">Requirements</span></span>  
 <span data-ttu-id="339bc-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="339bc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="339bc-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="339bc-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="339bc-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="339bc-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="339bc-122">**.NET framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="339bc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="339bc-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="339bc-123">See Also</span></span>  
 [<span data-ttu-id="339bc-124">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="339bc-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
