---
title: "ISymUnmanagedScope::GetStartOffset 方法"
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
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e0328af628eec062dc9efa7012bbeff213f1b86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="7c6e8-102">ISymUnmanagedScope::GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="7c6e8-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="7c6e8-103">获取此范围的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="7c6e8-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c6e8-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c6e8-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c6e8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7c6e8-106">[out]指向的指针`ULONG32`，其中包含的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="7c6e8-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c6e8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7c6e8-107">Return Value</span></span>  
 <span data-ttu-id="7c6e8-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="7c6e8-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c6e8-109">惠?</span><span class="sxs-lookup"><span data-stu-id="7c6e8-109">Requirements</span></span>  
 <span data-ttu-id="7c6e8-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7c6e8-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c6e8-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c6e8-111">See Also</span></span>  
 [<span data-ttu-id="7c6e8-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="7c6e8-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="7c6e8-113">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="7c6e8-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
