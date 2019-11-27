---
title: ISymUnmanagedENCUpdate::UpdateMethodLines 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
ms.openlocfilehash: 9aace77c4b3549c033433d4c305b07daa1f7a8c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448990"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="5f33b-102">ISymUnmanagedENCUpdate::UpdateMethodLines 方法</span><span class="sxs-lookup"><span data-stu-id="5f33b-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="5f33b-103">允许更新尚未重新编译但行已单独移动的方法的行信息。</span><span class="sxs-lookup"><span data-stu-id="5f33b-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="5f33b-104">允许每个语句的增量。</span><span class="sxs-lookup"><span data-stu-id="5f33b-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f33b-105">语法</span><span class="sxs-lookup"><span data-stu-id="5f33b-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f33b-106">参数</span><span class="sxs-lookup"><span data-stu-id="5f33b-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="5f33b-107">中方法标记的元数据。</span><span class="sxs-lookup"><span data-stu-id="5f33b-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="5f33b-108">中一个 `INT32` 值的数组，该值指示方法中的每个序列点的增量。</span><span class="sxs-lookup"><span data-stu-id="5f33b-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="5f33b-109">中包含 `pDeltas` 参数大小的 `ULONG`。</span><span class="sxs-lookup"><span data-stu-id="5f33b-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f33b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="5f33b-110">Return Value</span></span>  
 <span data-ttu-id="5f33b-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="5f33b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f33b-112">要求</span><span class="sxs-lookup"><span data-stu-id="5f33b-112">Requirements</span></span>  
 <span data-ttu-id="5f33b-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="5f33b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f33b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f33b-114">See also</span></span>

- [<span data-ttu-id="5f33b-115">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="5f33b-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
