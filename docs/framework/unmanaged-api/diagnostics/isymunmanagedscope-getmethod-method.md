---
title: "ISymUnmanagedScope::GetMethod 方法"
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
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4756ff1f373f09a96daa64c1fb01875274a6d0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="f0d49-102">ISymUnmanagedScope::GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="f0d49-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="f0d49-103">获取包含此作用域的方法。</span><span class="sxs-lookup"><span data-stu-id="f0d49-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0d49-104">语法</span><span class="sxs-lookup"><span data-stu-id="f0d49-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0d49-105">参数</span><span class="sxs-lookup"><span data-stu-id="f0d49-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f0d49-106">[out]指向返回的指针[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f0d49-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0d49-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f0d49-107">Return Value</span></span>  
 <span data-ttu-id="f0d49-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="f0d49-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0d49-109">惠?</span><span class="sxs-lookup"><span data-stu-id="f0d49-109">Requirements</span></span>  
 <span data-ttu-id="f0d49-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f0d49-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d49-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0d49-111">See Also</span></span>  
 [<span data-ttu-id="f0d49-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="f0d49-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
