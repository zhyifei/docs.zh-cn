---
title: "ISymUnmanagedScope::GetLocalCount 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetLocalCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9db774140ef55b2dfcb54ff701c2b842418a4923
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="49f8d-102">ISymUnmanagedScope::GetLocalCount 方法</span><span class="sxs-lookup"><span data-stu-id="49f8d-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="49f8d-103">获取此范围内定义的本地变量的计数。</span><span class="sxs-lookup"><span data-stu-id="49f8d-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="49f8d-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49f8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="49f8d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="49f8d-106">[out]指向的指针`ULONG32`接收本地变量的计数。</span><span class="sxs-lookup"><span data-stu-id="49f8d-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49f8d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="49f8d-107">Return Value</span></span>  
 <span data-ttu-id="49f8d-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="49f8d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49f8d-109">惠?</span><span class="sxs-lookup"><span data-stu-id="49f8d-109">Requirements</span></span>  
 <span data-ttu-id="49f8d-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="49f8d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f8d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="49f8d-111">See Also</span></span>  
 [<span data-ttu-id="49f8d-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="49f8d-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
