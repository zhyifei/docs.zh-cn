---
title: "ISymUnmanagedMethod::GetOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1c60d35b63d083ce4e23119e3fcb5e64c518f0ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="cc421-102">ISymUnmanagedMethod::GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="cc421-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="cc421-103">返回到文档内的给定位置在此方法的相对应的偏移量。</span><span class="sxs-lookup"><span data-stu-id="cc421-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc421-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc421-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc421-105">参数</span><span class="sxs-lookup"><span data-stu-id="cc421-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="cc421-106">[in]指向为其请求偏移量的文档的指针。</span><span class="sxs-lookup"><span data-stu-id="cc421-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="cc421-107">[in]为其请求偏移量的文档行。</span><span class="sxs-lookup"><span data-stu-id="cc421-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="cc421-108">[in]为其请求偏移量的文档列。</span><span class="sxs-lookup"><span data-stu-id="cc421-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="cc421-109">[out]指向的指针`ULONG32`接收偏移量。</span><span class="sxs-lookup"><span data-stu-id="cc421-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc421-110">返回值</span><span class="sxs-lookup"><span data-stu-id="cc421-110">Return Value</span></span>  
 <span data-ttu-id="cc421-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="cc421-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc421-112">惠?</span><span class="sxs-lookup"><span data-stu-id="cc421-112">Requirements</span></span>  
 <span data-ttu-id="cc421-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cc421-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc421-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc421-114">See Also</span></span>  
 [<span data-ttu-id="cc421-115">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="cc421-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
