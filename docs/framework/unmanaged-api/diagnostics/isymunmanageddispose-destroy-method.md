---
title: ISymUnmanagedDispose::Destroy 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51d2f0aedffdd88974a8184954ecbb9a231b70c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939940"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="73676-102">ISymUnmanagedDispose::Destroy 方法</span><span class="sxs-lookup"><span data-stu-id="73676-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="73676-103">导致要释放内部的所有引用和任何后续方法调用上返回失败的基础对象。</span><span class="sxs-lookup"><span data-stu-id="73676-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73676-104">语法</span><span class="sxs-lookup"><span data-stu-id="73676-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="73676-105">返回值</span><span class="sxs-lookup"><span data-stu-id="73676-105">Return Value</span></span>  
 <span data-ttu-id="73676-106">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="73676-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73676-107">要求</span><span class="sxs-lookup"><span data-stu-id="73676-107">Requirements</span></span>  
 <span data-ttu-id="73676-108">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="73676-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73676-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="73676-109">See also</span></span>

- [<span data-ttu-id="73676-110">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="73676-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
