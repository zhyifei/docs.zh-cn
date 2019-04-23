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
ms.openlocfilehash: 7f470dbe4ef2ef0d5f2204ccbdd5fb64730f9a2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159752"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="da10a-102">ISymUnmanagedWriter::DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="da10a-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="da10a-103">定义常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="da10a-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da10a-104">语法</span><span class="sxs-lookup"><span data-stu-id="da10a-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da10a-105">参数</span><span class="sxs-lookup"><span data-stu-id="da10a-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="da10a-106">[in]一个指向`WCHAR`，用于定义该常量的名称。</span><span class="sxs-lookup"><span data-stu-id="da10a-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="da10a-107">[in]常量的值。</span><span class="sxs-lookup"><span data-stu-id="da10a-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="da10a-108">[in] `signature` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="da10a-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="da10a-109">[in]常量类型签名。</span><span class="sxs-lookup"><span data-stu-id="da10a-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da10a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="da10a-110">Return Value</span></span>  
 <span data-ttu-id="da10a-111">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="da10a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da10a-112">要求</span><span class="sxs-lookup"><span data-stu-id="da10a-112">Requirements</span></span>  
 <span data-ttu-id="da10a-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="da10a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da10a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="da10a-114">See also</span></span>

- [<span data-ttu-id="da10a-115">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="da10a-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="da10a-116">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="da10a-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
