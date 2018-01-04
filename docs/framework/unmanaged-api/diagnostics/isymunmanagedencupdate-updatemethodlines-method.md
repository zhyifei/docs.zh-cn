---
title: "ISymUnmanagedENCUpdate::UpdateMethodLines 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.UpdateMethodLines
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e8ffecba62b6531c852e6510013ba56b9258b64
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="d2dd8-102">ISymUnmanagedENCUpdate::UpdateMethodLines 方法</span><span class="sxs-lookup"><span data-stu-id="d2dd8-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="d2dd8-103">允许更新的方法，不重新编译，但其行已独立移动的行信息。</span><span class="sxs-lookup"><span data-stu-id="d2dd8-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="d2dd8-104">允许的 delta 的每个语句。</span><span class="sxs-lookup"><span data-stu-id="d2dd8-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2dd8-105">语法</span><span class="sxs-lookup"><span data-stu-id="d2dd8-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2dd8-106">参数</span><span class="sxs-lookup"><span data-stu-id="d2dd8-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="d2dd8-107">[in]方法令牌的元数据。</span><span class="sxs-lookup"><span data-stu-id="d2dd8-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="d2dd8-108">[in]数组`INT32`值，该值指示方法中的每个序列点的增量。</span><span class="sxs-lookup"><span data-stu-id="d2dd8-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="d2dd8-109">[in]A`ULONG`包含的大小`pDeltas`参数。</span><span class="sxs-lookup"><span data-stu-id="d2dd8-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2dd8-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d2dd8-110">Return Value</span></span>  
 <span data-ttu-id="d2dd8-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="d2dd8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2dd8-112">惠?</span><span class="sxs-lookup"><span data-stu-id="d2dd8-112">Requirements</span></span>  
 <span data-ttu-id="d2dd8-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d2dd8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2dd8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2dd8-114">See Also</span></span>  
 [<span data-ttu-id="d2dd8-115">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="d2dd8-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
