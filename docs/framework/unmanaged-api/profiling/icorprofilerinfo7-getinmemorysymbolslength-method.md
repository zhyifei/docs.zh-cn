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
ms.openlocfilehash: 422fdfef6bea40e0f4bcc7447df8dba1eab2896e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146089"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="72b88-102">ICorProfilerInfo7::GetInMemorySymbolsLength 方法</span><span class="sxs-lookup"><span data-stu-id="72b88-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="72b88-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="72b88-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="72b88-104">返回内存中的符号流的长度。</span><span class="sxs-lookup"><span data-stu-id="72b88-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72b88-105">语法</span><span class="sxs-lookup"><span data-stu-id="72b88-105">Syntax</span></span>  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72b88-106">参数</span><span class="sxs-lookup"><span data-stu-id="72b88-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="72b88-107">[in]包含内存中流的模块标识符。</span><span class="sxs-lookup"><span data-stu-id="72b88-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="72b88-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="72b88-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="72b88-109">[out]一个指向`DWORD`值，该值，方法返回时，包含以字节为单位的流的长度。</span><span class="sxs-lookup"><span data-stu-id="72b88-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72b88-110">返回值</span><span class="sxs-lookup"><span data-stu-id="72b88-110">Return Value</span></span>  
 <span data-ttu-id="72b88-111">该方法将返回`S_OK`如果内存流的长度就可以确定，即使它是零 (0)。</span><span class="sxs-lookup"><span data-stu-id="72b88-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="72b88-112">该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`如果该方法使用创建<xref:System.Reflection.Emit?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="72b88-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72b88-113">备注</span><span class="sxs-lookup"><span data-stu-id="72b88-113">Remarks</span></span>  
 <span data-ttu-id="72b88-114">如果模块有内存中的符号，流的长度位于`pCountSymbolBytes`。</span><span class="sxs-lookup"><span data-stu-id="72b88-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="72b88-115">如果该模块没有内存中的符号， `*pCountSymbolBytes = 0`。</span><span class="sxs-lookup"><span data-stu-id="72b88-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72b88-116">当前实现不支持 Reflection.Emit。</span><span class="sxs-lookup"><span data-stu-id="72b88-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="72b88-117">如果通过使用 Reflection.Emit 创建模块，该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`。</span><span class="sxs-lookup"><span data-stu-id="72b88-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72b88-118">要求</span><span class="sxs-lookup"><span data-stu-id="72b88-118">Requirements</span></span>  
 <span data-ttu-id="72b88-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72b88-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72b88-120">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72b88-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72b88-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72b88-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="72b88-122">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="72b88-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72b88-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="72b88-123">See also</span></span>

- [<span data-ttu-id="72b88-124">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="72b88-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
