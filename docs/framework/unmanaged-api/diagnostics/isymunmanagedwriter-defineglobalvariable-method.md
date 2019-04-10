---
title: ISymUnmanagedWriter::DefineGlobalVariable 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66efe5ae1fe2154684d2ac6791895b7fcbe4f7b6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225908"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="28f42-102">ISymUnmanagedWriter::DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="28f42-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="28f42-103">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="28f42-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f42-104">语法</span><span class="sxs-lookup"><span data-stu-id="28f42-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="28f42-105">参数</span><span class="sxs-lookup"><span data-stu-id="28f42-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="28f42-106">[in]一个指向`WCHAR`，用于定义全局变量的名称。</span><span class="sxs-lookup"><span data-stu-id="28f42-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="28f42-107">[in]全局变量特性。</span><span class="sxs-lookup"><span data-stu-id="28f42-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="28f42-108">[in]一个`ULONG32`指示的大小，以字符为单位的`signature`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="28f42-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="28f42-109">[in]全局变量签名。</span><span class="sxs-lookup"><span data-stu-id="28f42-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="28f42-110">[in]地址类型。</span><span class="sxs-lookup"><span data-stu-id="28f42-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="28f42-111">[in]参数规格的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="28f42-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="28f42-112">[in]参数规格的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="28f42-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="28f42-113">[in]参数规格的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="28f42-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28f42-114">返回值</span><span class="sxs-lookup"><span data-stu-id="28f42-114">Return Value</span></span>  
 <span data-ttu-id="28f42-115">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="28f42-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f42-116">要求</span><span class="sxs-lookup"><span data-stu-id="28f42-116">Requirements</span></span>  
 <span data-ttu-id="28f42-117">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="28f42-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f42-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="28f42-118">See also</span></span>

- [<span data-ttu-id="28f42-119">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="28f42-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="28f42-120">DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="28f42-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="28f42-121">DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="28f42-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)
