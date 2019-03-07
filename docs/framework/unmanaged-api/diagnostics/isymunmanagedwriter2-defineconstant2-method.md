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
ms.openlocfilehash: 6674c706222fe9e00a0115bef83f955384f14172
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485339"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="0df91-102">ISymUnmanagedWriter2::DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="0df91-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="0df91-103">定义常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="0df91-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0df91-104">语法</span><span class="sxs-lookup"><span data-stu-id="0df91-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0df91-105">参数</span><span class="sxs-lookup"><span data-stu-id="0df91-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="0df91-106">[in]该常量的名称。</span><span class="sxs-lookup"><span data-stu-id="0df91-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="0df91-107">[in]常量的值。</span><span class="sxs-lookup"><span data-stu-id="0df91-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="0df91-108">[in]常量的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="0df91-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0df91-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0df91-109">Return Value</span></span>  
 <span data-ttu-id="0df91-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="0df91-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0df91-111">要求</span><span class="sxs-lookup"><span data-stu-id="0df91-111">Requirements</span></span>  
 <span data-ttu-id="0df91-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0df91-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df91-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0df91-113">See also</span></span>
- [<span data-ttu-id="0df91-114">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="0df91-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="0df91-115">DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="0df91-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
