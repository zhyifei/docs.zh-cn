---
title: "ISymUnmanagedWriter::DefineLocalVariable 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineLocalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e454aa2c2dd8ceb8f8dbbc03bdd1e70e8a800de2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="b6de7-102">ISymUnmanagedWriter::DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="b6de7-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="b6de7-103">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="b6de7-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="b6de7-104">在范围内具有多个 home 具有相同名称的变量，此方法可以调用多次。</span><span class="sxs-lookup"><span data-stu-id="b6de7-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="b6de7-105">在此情况下，但是，值`startOffset`和`endOffset`参数不能重叠。</span><span class="sxs-lookup"><span data-stu-id="b6de7-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6de7-106">语法</span><span class="sxs-lookup"><span data-stu-id="b6de7-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6de7-107">参数</span><span class="sxs-lookup"><span data-stu-id="b6de7-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b6de7-108">[in]指向的指针`WCHAR`，它定义的本地变量的名称。</span><span class="sxs-lookup"><span data-stu-id="b6de7-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="b6de7-109">[in]本地变量的特性。</span><span class="sxs-lookup"><span data-stu-id="b6de7-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="b6de7-110">[in]A`ULONG32`指示的大小，以字节为单位，`signature`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b6de7-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="b6de7-111">[in]局部变量签名。</span><span class="sxs-lookup"><span data-stu-id="b6de7-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="b6de7-112">[in]地址类型中。</span><span class="sxs-lookup"><span data-stu-id="b6de7-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="b6de7-113">[in]参数规格的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="b6de7-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="b6de7-114">[in]参数规范第二个地址。</span><span class="sxs-lookup"><span data-stu-id="b6de7-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="b6de7-115">[in]参数规格的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="b6de7-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="b6de7-116">[in]变量起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="b6de7-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="b6de7-117">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="b6de7-117">This parameter is optional.</span></span> <span data-ttu-id="b6de7-118">如果该值为 0，将忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="b6de7-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="b6de7-119">如果它为非零值，该变量将位于偏移量的当前作用域内。</span><span class="sxs-lookup"><span data-stu-id="b6de7-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="b6de7-120">[in]变量结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="b6de7-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="b6de7-121">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="b6de7-121">This parameter is optional.</span></span> <span data-ttu-id="b6de7-122">如果该值为 0，将忽略此参数，并在整个范围内定义变量。</span><span class="sxs-lookup"><span data-stu-id="b6de7-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="b6de7-123">如果它为非零值，该变量将位于偏移量的当前作用域内。</span><span class="sxs-lookup"><span data-stu-id="b6de7-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6de7-124">返回值</span><span class="sxs-lookup"><span data-stu-id="b6de7-124">Return Value</span></span>  
 <span data-ttu-id="b6de7-125">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="b6de7-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6de7-126">要求</span><span class="sxs-lookup"><span data-stu-id="b6de7-126">Requirements</span></span>  
 <span data-ttu-id="b6de7-127">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6de7-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6de7-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6de7-128">See Also</span></span>  
 [<span data-ttu-id="b6de7-129">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="b6de7-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="b6de7-130">DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="b6de7-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [<span data-ttu-id="b6de7-131">DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="b6de7-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
