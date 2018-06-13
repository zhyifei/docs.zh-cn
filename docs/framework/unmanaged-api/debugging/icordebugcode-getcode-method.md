---
title: ICorDebugCode::GetCode 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d09681f97829f88bedf53af229298d5d57d764df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402684"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="e8d2d-102">ICorDebugCode::GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="e8d2d-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="e8d2d-103">获取为指定的函数，为反汇编进行格式化的所有代码。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="e8d2d-104">.NET Framework 2.0 版中，此方法已被否决。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e8d2d-105">使用[icordebugcode2:: Getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-105">Use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d2d-106">语法</span><span class="sxs-lookup"><span data-stu-id="e8d2d-106">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8d2d-107">参数</span><span class="sxs-lookup"><span data-stu-id="e8d2d-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="e8d2d-108">[in]函数的开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="e8d2d-109">[in]在函数末尾的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="e8d2d-110">[in]大小`buffer`数组转换返回的代码。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="e8d2d-111">[out]代码将返回到其中的数组。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="e8d2d-112">[out]返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8d2d-113">备注</span><span class="sxs-lookup"><span data-stu-id="e8d2d-113">Remarks</span></span>  
 <span data-ttu-id="e8d2d-114">如果该函数的代码具有已划分为多个块区中，它们被串联本机偏移递增的顺序。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="e8d2d-115">不检查指令边界。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8d2d-116">要求</span><span class="sxs-lookup"><span data-stu-id="e8d2d-116">Requirements</span></span>  
 <span data-ttu-id="e8d2d-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8d2d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8d2d-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8d2d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8d2d-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8d2d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8d2d-120">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="e8d2d-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d2d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8d2d-121">See Also</span></span>  
 [<span data-ttu-id="e8d2d-122">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="e8d2d-122">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 
