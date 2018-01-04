---
title: "ISymUnmanagedWriter2::DefineConstant2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineConstant2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1b3e5ea28092be1ea8bc2629b4ee6f08cd630b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="61dda-102">ISymUnmanagedWriter2::DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="61dda-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="61dda-103">定义的常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="61dda-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61dda-104">语法</span><span class="sxs-lookup"><span data-stu-id="61dda-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61dda-105">参数</span><span class="sxs-lookup"><span data-stu-id="61dda-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="61dda-106">[in]该常量的名称。</span><span class="sxs-lookup"><span data-stu-id="61dda-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="61dda-107">[in]常量的值。</span><span class="sxs-lookup"><span data-stu-id="61dda-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="61dda-108">[in]常量元数据标记。</span><span class="sxs-lookup"><span data-stu-id="61dda-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61dda-109">返回值</span><span class="sxs-lookup"><span data-stu-id="61dda-109">Return Value</span></span>  
 <span data-ttu-id="61dda-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="61dda-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61dda-111">惠?</span><span class="sxs-lookup"><span data-stu-id="61dda-111">Requirements</span></span>  
 <span data-ttu-id="61dda-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="61dda-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61dda-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="61dda-113">See Also</span></span>  
 [<span data-ttu-id="61dda-114">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="61dda-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="61dda-115">DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="61dda-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
