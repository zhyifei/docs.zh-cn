---
title: ISymUnmanagedWriter2::DefineConstant2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e843acc82d52e2c7a772f4799e7bb0af8ecff10d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545720"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="c2bc1-102">ISymUnmanagedWriter2::DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="c2bc1-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="c2bc1-103">定义常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="c2bc1-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2bc1-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2bc1-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2bc1-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2bc1-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="c2bc1-106">[in]该常量的名称。</span><span class="sxs-lookup"><span data-stu-id="c2bc1-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="c2bc1-107">[in]常量的值。</span><span class="sxs-lookup"><span data-stu-id="c2bc1-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="c2bc1-108">[in]常量的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="c2bc1-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2bc1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c2bc1-109">Return Value</span></span>  
 <span data-ttu-id="c2bc1-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c2bc1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2bc1-111">要求</span><span class="sxs-lookup"><span data-stu-id="c2bc1-111">Requirements</span></span>  
 <span data-ttu-id="c2bc1-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c2bc1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2bc1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2bc1-113">See also</span></span>
- [<span data-ttu-id="c2bc1-114">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="c2bc1-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="c2bc1-115">DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="c2bc1-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
