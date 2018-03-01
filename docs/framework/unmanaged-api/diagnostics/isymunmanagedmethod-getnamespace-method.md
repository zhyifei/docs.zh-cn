---
title: "ISymUnmanagedMethod::GetNamespace 方法"
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
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2244229b50a9944cefb5804720198bf391fd0e6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="e32e1-102">ISymUnmanagedMethod::GetNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="e32e1-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="e32e1-103">获取在其中定义此方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e32e1-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="e32e1-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e32e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="e32e1-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e32e1-106">[out]一个指针，它设置为返回[ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e32e1-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e32e1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e32e1-107">Return Value</span></span>  
 <span data-ttu-id="e32e1-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e32e1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e32e1-109">惠?</span><span class="sxs-lookup"><span data-stu-id="e32e1-109">Requirements</span></span>  
 <span data-ttu-id="e32e1-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e32e1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32e1-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e32e1-111">See Also</span></span>  
 [<span data-ttu-id="e32e1-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="e32e1-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
