---
title: ICorProfilerInfo7：： GetInMemorySymbolsLength 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: a675cc301d2dd32f87e3864a3123e2044761ef91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868351"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="3f3ee-102">ICorProfilerInfo7：： GetInMemorySymbolsLength 方法</span><span class="sxs-lookup"><span data-stu-id="3f3ee-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="3f3ee-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="3f3ee-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="3f3ee-104">返回内存中符号流的长度。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f3ee-105">语法</span><span class="sxs-lookup"><span data-stu-id="3f3ee-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f3ee-106">参数</span><span class="sxs-lookup"><span data-stu-id="3f3ee-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="3f3ee-107">中包含内存中流的模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="3f3ee-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="3f3ee-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="3f3ee-109">弄一个指向 `DWORD` 值的指针，当该方法返回时，将包含流的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f3ee-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3f3ee-110">Return Value</span></span>  
 <span data-ttu-id="3f3ee-111">如果可以确定内存流的长度，则该方法将返回 `S_OK` （即使它是零（0））。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="3f3ee-112">如果该方法是使用 <xref:System.Reflection.Emit?displayProperty=nameWithType>创建的，则该方法将返回 `CORPROF_E_MODULE_IS_DYNAMIC`。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f3ee-113">备注</span><span class="sxs-lookup"><span data-stu-id="3f3ee-113">Remarks</span></span>  
 <span data-ttu-id="3f3ee-114">如果模块有内存中符号，则流的长度将置于 `pCountSymbolBytes`中。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="3f3ee-115">如果模块没有内存中符号，请 `*pCountSymbolBytes = 0`。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f3ee-116">当前实现不支持反射。发出。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="3f3ee-117">如果该模块是使用反射创建的，则该方法将返回 `CORPROF_E_MODULE_IS_DYNAMIC`。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f3ee-118">需求</span><span class="sxs-lookup"><span data-stu-id="3f3ee-118">Requirements</span></span>  
 <span data-ttu-id="3f3ee-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f3ee-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f3ee-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f3ee-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f3ee-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f3ee-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f3ee-122">**.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f3ee-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f3ee-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f3ee-123">See also</span></span>

- [<span data-ttu-id="3f3ee-124">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="3f3ee-124">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
