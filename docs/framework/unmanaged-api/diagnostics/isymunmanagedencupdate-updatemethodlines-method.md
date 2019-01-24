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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7905b3ee83378ed1a27501b082dbfca01d6436c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688059"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="551aa-102">ISymUnmanagedENCUpdate::UpdateMethodLines 方法</span><span class="sxs-lookup"><span data-stu-id="551aa-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="551aa-103">允许更新的方法，已不被重新编译，但其行已独立移动的行信息。</span><span class="sxs-lookup"><span data-stu-id="551aa-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="551aa-104">允许每个语句的增量。</span><span class="sxs-lookup"><span data-stu-id="551aa-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="551aa-105">语法</span><span class="sxs-lookup"><span data-stu-id="551aa-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="551aa-106">参数</span><span class="sxs-lookup"><span data-stu-id="551aa-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="551aa-107">[in]方法令牌的元数据。</span><span class="sxs-lookup"><span data-stu-id="551aa-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="551aa-108">[in]一个数组`INT32`值，该值指示方法中的每个序列点的增量。</span><span class="sxs-lookup"><span data-stu-id="551aa-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="551aa-109">[in]一个`ULONG`包含的大小`pDeltas`参数。</span><span class="sxs-lookup"><span data-stu-id="551aa-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="551aa-110">返回值</span><span class="sxs-lookup"><span data-stu-id="551aa-110">Return Value</span></span>  
 <span data-ttu-id="551aa-111">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="551aa-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="551aa-112">要求</span><span class="sxs-lookup"><span data-stu-id="551aa-112">Requirements</span></span>  
 <span data-ttu-id="551aa-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="551aa-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="551aa-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="551aa-114">See also</span></span>
- [<span data-ttu-id="551aa-115">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="551aa-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
