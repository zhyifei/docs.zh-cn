---
title: "ICorDebugCode2::GetCodeChunks 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode2.GetCodeChunks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 950fd5c19e8827a63dcf075c42d3e0c18ff91261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="6a343-102">ICorDebugCode2::GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="6a343-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="6a343-103">获取此代码对象组成的代码块。</span><span class="sxs-lookup"><span data-stu-id="6a343-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a343-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a343-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a343-105">参数</span><span class="sxs-lookup"><span data-stu-id="6a343-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="6a343-106">[in]大小`chunks`数组。</span><span class="sxs-lookup"><span data-stu-id="6a343-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="6a343-107">[out]在中返回的区块的数量`chunks`数组。</span><span class="sxs-lookup"><span data-stu-id="6a343-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="6a343-108">[out]"CodeChunkInfo"结构数组，其中每个表示的单一代码块。</span><span class="sxs-lookup"><span data-stu-id="6a343-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="6a343-109">如果值`cbufSize`为 0，此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="6a343-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a343-110">备注</span><span class="sxs-lookup"><span data-stu-id="6a343-110">Remarks</span></span>  
 <span data-ttu-id="6a343-111">代码块将永远不会重叠，而且它们将遵循的顺序，它们将连接通过公共[icordebugcode::](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)。</span><span class="sxs-lookup"><span data-stu-id="6a343-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="6a343-112">.NET Framework 2.0 版中的 Microsoft 中间语言 (MSIL) 代码对象将构成单个代码块。</span><span class="sxs-lookup"><span data-stu-id="6a343-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a343-113">要求</span><span class="sxs-lookup"><span data-stu-id="6a343-113">Requirements</span></span>  
 <span data-ttu-id="6a343-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a343-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a343-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a343-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a343-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a343-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a343-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a343-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a343-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a343-118">See Also</span></span>  
 
