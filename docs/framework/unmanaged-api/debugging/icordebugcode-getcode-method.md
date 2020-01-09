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
ms.openlocfilehash: db24228de7e8c98fd97f890b1e408515172299b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125669"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="5dc29-102">ICorDebugCode::GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="5dc29-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="5dc29-103">获取用于反汇编的指定函数的所有代码。</span><span class="sxs-lookup"><span data-stu-id="5dc29-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="5dc29-104">此方法在 .NET Framework 版本2.0 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="5dc29-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="5dc29-105">改[为使用 ICorDebugCode2：： GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="5dc29-105">Use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dc29-106">语法</span><span class="sxs-lookup"><span data-stu-id="5dc29-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dc29-107">参数</span><span class="sxs-lookup"><span data-stu-id="5dc29-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="5dc29-108">中函数开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="5dc29-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="5dc29-109">中函数末尾的偏移量。</span><span class="sxs-lookup"><span data-stu-id="5dc29-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="5dc29-110">中将返回代码的 `buffer` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="5dc29-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="5dc29-111">弄将向其中返回代码的数组。</span><span class="sxs-lookup"><span data-stu-id="5dc29-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="5dc29-112">弄返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="5dc29-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dc29-113">备注</span><span class="sxs-lookup"><span data-stu-id="5dc29-113">Remarks</span></span>  
 <span data-ttu-id="5dc29-114">如果函数的代码已划分为多个块，则它们将按照增加的本机偏移量的顺序进行连接。</span><span class="sxs-lookup"><span data-stu-id="5dc29-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="5dc29-115">不检查指令边界。</span><span class="sxs-lookup"><span data-stu-id="5dc29-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dc29-116">要求</span><span class="sxs-lookup"><span data-stu-id="5dc29-116">Requirements</span></span>  
 <span data-ttu-id="5dc29-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5dc29-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc29-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5dc29-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5dc29-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5dc29-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5dc29-120">**.NET Framework 版本：** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="5dc29-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc29-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5dc29-121">See also</span></span>

- [<span data-ttu-id="5dc29-122">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="5dc29-122">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
