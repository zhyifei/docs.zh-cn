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
ms.openlocfilehash: e03339ff2c1205f66281bd31c3ef67439feea39c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726477"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="b7c30-102">ISymUnmanagedWriter::DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="b7c30-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="b7c30-103">定义常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="b7c30-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7c30-104">语法</span><span class="sxs-lookup"><span data-stu-id="b7c30-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7c30-105">参数</span><span class="sxs-lookup"><span data-stu-id="b7c30-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b7c30-106">[in]一个指向`WCHAR`，用于定义该常量的名称。</span><span class="sxs-lookup"><span data-stu-id="b7c30-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="b7c30-107">[in]常量的值。</span><span class="sxs-lookup"><span data-stu-id="b7c30-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="b7c30-108">[in] `signature` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="b7c30-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="b7c30-109">[in]常量类型签名。</span><span class="sxs-lookup"><span data-stu-id="b7c30-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7c30-110">返回值</span><span class="sxs-lookup"><span data-stu-id="b7c30-110">Return Value</span></span>  
 <span data-ttu-id="b7c30-111">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="b7c30-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7c30-112">要求</span><span class="sxs-lookup"><span data-stu-id="b7c30-112">Requirements</span></span>  
 <span data-ttu-id="b7c30-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b7c30-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c30-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7c30-114">See also</span></span>
- [<span data-ttu-id="b7c30-115">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="b7c30-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="b7c30-116">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="b7c30-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
