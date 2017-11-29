---
title: "ISymUnmanagedWriter::DefineConstant 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineConstant
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 910f2e753849b955a398f2175342b2f94849fba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="50393-102">ISymUnmanagedWriter::DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="50393-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="50393-103">定义的常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="50393-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50393-104">语法</span><span class="sxs-lookup"><span data-stu-id="50393-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50393-105">参数</span><span class="sxs-lookup"><span data-stu-id="50393-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="50393-106">[in]指向的指针`WCHAR`定义该常量的名称。</span><span class="sxs-lookup"><span data-stu-id="50393-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="50393-107">[in]常量的值。</span><span class="sxs-lookup"><span data-stu-id="50393-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="50393-108">[in] `signature` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="50393-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="50393-109">[in]常量类型签名。</span><span class="sxs-lookup"><span data-stu-id="50393-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50393-110">返回值</span><span class="sxs-lookup"><span data-stu-id="50393-110">Return Value</span></span>  
 <span data-ttu-id="50393-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="50393-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50393-112">要求</span><span class="sxs-lookup"><span data-stu-id="50393-112">Requirements</span></span>  
 <span data-ttu-id="50393-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="50393-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50393-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50393-114">See Also</span></span>  
 [<span data-ttu-id="50393-115">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="50393-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="50393-116">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="50393-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
