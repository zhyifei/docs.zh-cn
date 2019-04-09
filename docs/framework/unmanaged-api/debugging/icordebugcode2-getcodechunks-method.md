---
title: ICorDebugCode2::GetCodeChunks 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1428fc245d4f6993050c2753321684afee488c0e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116776"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="54d1f-102">ICorDebugCode2::GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="54d1f-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="54d1f-103">获取此代码对象组成的代码块。</span><span class="sxs-lookup"><span data-stu-id="54d1f-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d1f-104">语法</span><span class="sxs-lookup"><span data-stu-id="54d1f-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54d1f-105">参数</span><span class="sxs-lookup"><span data-stu-id="54d1f-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="54d1f-106">[in]大小`chunks`数组。</span><span class="sxs-lookup"><span data-stu-id="54d1f-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="54d1f-107">[out]在中返回的消息块数量`chunks`数组。</span><span class="sxs-lookup"><span data-stu-id="54d1f-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="54d1f-108">[out]"CodeChunkInfo"结构数组，其中每个表示单个代码块。</span><span class="sxs-lookup"><span data-stu-id="54d1f-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="54d1f-109">如果的值`cbufSize`为 0，则此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="54d1f-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54d1f-110">备注</span><span class="sxs-lookup"><span data-stu-id="54d1f-110">Remarks</span></span>  
 <span data-ttu-id="54d1f-111">代码块将永远不会重叠，而且它们将遵循在其中它们将具有已连接起来的顺序[icordebugcode:: Getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)。</span><span class="sxs-lookup"><span data-stu-id="54d1f-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="54d1f-112">.NET Framework 2.0 版中的 Microsoft 中间语言 (MSIL) 代码对象将包含单个代码块。</span><span class="sxs-lookup"><span data-stu-id="54d1f-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54d1f-113">要求</span><span class="sxs-lookup"><span data-stu-id="54d1f-113">Requirements</span></span>  
 <span data-ttu-id="54d1f-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54d1f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54d1f-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54d1f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54d1f-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54d1f-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="54d1f-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="54d1f-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="54d1f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="54d1f-118">See also</span></span>
