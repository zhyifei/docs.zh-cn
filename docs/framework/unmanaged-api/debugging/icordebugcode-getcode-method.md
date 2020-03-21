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
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179002"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="04003-102">ICorDebugCode::GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="04003-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="04003-103">获取指定函数的所有代码，这些代码为拆卸格式化。</span><span class="sxs-lookup"><span data-stu-id="04003-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="04003-104">此方法已在 .NET 框架版本 2.0 中弃用。</span><span class="sxs-lookup"><span data-stu-id="04003-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="04003-105">使用[ICorDebugCode2：：请改为获取代码块](icordebugcode2-getcodechunks-method.md)。</span><span class="sxs-lookup"><span data-stu-id="04003-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04003-106">语法</span><span class="sxs-lookup"><span data-stu-id="04003-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="04003-107">parameters</span><span class="sxs-lookup"><span data-stu-id="04003-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="04003-108">[在]函数开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="04003-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="04003-109">[在]函数末尾的偏移量。</span><span class="sxs-lookup"><span data-stu-id="04003-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="04003-110">[在]要将代码返回到`buffer`的数组的大小。</span><span class="sxs-lookup"><span data-stu-id="04003-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="04003-111">[出]将代码返回到的数组。</span><span class="sxs-lookup"><span data-stu-id="04003-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="04003-112">[出]返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="04003-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04003-113">备注</span><span class="sxs-lookup"><span data-stu-id="04003-113">Remarks</span></span>  
 <span data-ttu-id="04003-114">如果函数的代码已划分为多个区块，则它们按增加本机偏移的顺序串联。</span><span class="sxs-lookup"><span data-stu-id="04003-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="04003-115">未检查指令边界。</span><span class="sxs-lookup"><span data-stu-id="04003-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04003-116">要求</span><span class="sxs-lookup"><span data-stu-id="04003-116">Requirements</span></span>  
 <span data-ttu-id="04003-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="04003-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04003-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04003-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04003-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04003-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04003-120">**.NET 框架版本：** 1.1， 1.0</span><span class="sxs-lookup"><span data-stu-id="04003-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04003-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04003-121">See also</span></span>

- [<span data-ttu-id="04003-122">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="04003-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
