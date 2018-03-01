---
title: "ISymUnmanagedDispose::Destroy 方法"
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
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8d418bbb476fea306bf9ad92ce2b30d558627009
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="a1b8b-102">ISymUnmanagedDispose::Destroy 方法</span><span class="sxs-lookup"><span data-stu-id="a1b8b-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="a1b8b-103">导致要释放所有内部引用，并在任何后续方法调用返回失败的基础对象。</span><span class="sxs-lookup"><span data-stu-id="a1b8b-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1b8b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1b8b-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a1b8b-105">返回值</span><span class="sxs-lookup"><span data-stu-id="a1b8b-105">Return Value</span></span>  
 <span data-ttu-id="a1b8b-106">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="a1b8b-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1b8b-107">惠?</span><span class="sxs-lookup"><span data-stu-id="a1b8b-107">Requirements</span></span>  
 <span data-ttu-id="a1b8b-108">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a1b8b-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b8b-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1b8b-109">See Also</span></span>  
 [<span data-ttu-id="a1b8b-110">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="a1b8b-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
