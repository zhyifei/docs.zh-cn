---
title: ISymUnmanagedWriter::DefineConstant 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c7cf800dafa9f3e213a012f49c73d51c78e7074
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427400"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="707c5-102">ISymUnmanagedWriter::DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="707c5-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="707c5-103">定义的常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="707c5-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="707c5-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="707c5-105">参数</span><span class="sxs-lookup"><span data-stu-id="707c5-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="707c5-106">[in]指向的指针`WCHAR`定义该常量的名称。</span><span class="sxs-lookup"><span data-stu-id="707c5-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="707c5-107">[in]常量的值。</span><span class="sxs-lookup"><span data-stu-id="707c5-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="707c5-108">[in] `signature` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="707c5-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="707c5-109">[in]常量类型签名。</span><span class="sxs-lookup"><span data-stu-id="707c5-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="707c5-110">返回值</span><span class="sxs-lookup"><span data-stu-id="707c5-110">Return Value</span></span>  
 <span data-ttu-id="707c5-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="707c5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707c5-112">要求</span><span class="sxs-lookup"><span data-stu-id="707c5-112">Requirements</span></span>  
 <span data-ttu-id="707c5-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="707c5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707c5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="707c5-114">See Also</span></span>  
 [<span data-ttu-id="707c5-115">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="707c5-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="707c5-116">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="707c5-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
