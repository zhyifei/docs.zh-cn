---
title: "ISymUnmanagedWriter2::DefineGlobalVariable2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineGlobalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d1214a7bc8cb2826e31c310c88bce8158aefd4f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="d2c9d-102">ISymUnmanagedWriter2::DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="d2c9d-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="d2c9d-103">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="d2c9d-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2c9d-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2c9d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d2c9d-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d2c9d-106">[in]全局变量名称。</span><span class="sxs-lookup"><span data-stu-id="d2c9d-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="d2c9d-107">[in]全局变量特性。</span><span class="sxs-lookup"><span data-stu-id="d2c9d-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="d2c9d-108">[in]签名的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d2c9d-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="d2c9d-109">[in]地址类型中。</span><span class="sxs-lookup"><span data-stu-id="d2c9d-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="d2c9d-110">[in]参数规格的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="d2c9d-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="d2c9d-111">[in]参数规范第二个地址。</span><span class="sxs-lookup"><span data-stu-id="d2c9d-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="d2c9d-112">[in]参数规格的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="d2c9d-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2c9d-113">返回值</span><span class="sxs-lookup"><span data-stu-id="d2c9d-113">Return Value</span></span>  
 <span data-ttu-id="d2c9d-114">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="d2c9d-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c9d-115">要求</span><span class="sxs-lookup"><span data-stu-id="d2c9d-115">Requirements</span></span>  
 <span data-ttu-id="d2c9d-116">**标头：** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="d2c9d-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c9d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2c9d-117">See Also</span></span>  
 [<span data-ttu-id="d2c9d-118">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="d2c9d-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="d2c9d-119">DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="d2c9d-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
