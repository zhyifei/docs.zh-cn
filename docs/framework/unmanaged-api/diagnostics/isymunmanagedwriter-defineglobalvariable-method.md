---
title: "ISymUnmanagedWriter::DefineGlobalVariable 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineGlobalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7540dfcefbe7a331a26220a07b2e206c1302ddc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="8eb60-102">ISymUnmanagedWriter::DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="8eb60-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="8eb60-103">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="8eb60-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eb60-104">语法</span><span class="sxs-lookup"><span data-stu-id="8eb60-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8eb60-105">参数</span><span class="sxs-lookup"><span data-stu-id="8eb60-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8eb60-106">[in]指向的指针`WCHAR`定义全局变量的名称。</span><span class="sxs-lookup"><span data-stu-id="8eb60-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="8eb60-107">[in]全局变量特性。</span><span class="sxs-lookup"><span data-stu-id="8eb60-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="8eb60-108">[in]A`ULONG32`指示的大小，以字符为单位的`signature`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8eb60-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="8eb60-109">[in]全局变量签名。</span><span class="sxs-lookup"><span data-stu-id="8eb60-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="8eb60-110">[in]地址类型中。</span><span class="sxs-lookup"><span data-stu-id="8eb60-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="8eb60-111">[in]参数规格的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="8eb60-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="8eb60-112">[in]参数规范第二个地址。</span><span class="sxs-lookup"><span data-stu-id="8eb60-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="8eb60-113">[in]参数规格的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="8eb60-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8eb60-114">返回值</span><span class="sxs-lookup"><span data-stu-id="8eb60-114">Return Value</span></span>  
 <span data-ttu-id="8eb60-115">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="8eb60-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eb60-116">要求</span><span class="sxs-lookup"><span data-stu-id="8eb60-116">Requirements</span></span>  
 <span data-ttu-id="8eb60-117">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8eb60-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb60-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8eb60-118">See Also</span></span>  
 [<span data-ttu-id="8eb60-119">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="8eb60-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="8eb60-120">DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="8eb60-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)  
 [<span data-ttu-id="8eb60-121">DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="8eb60-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)
