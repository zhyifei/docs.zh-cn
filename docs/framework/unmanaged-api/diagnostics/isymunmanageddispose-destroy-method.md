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
ms.openlocfilehash: 6a4a0bac056c7c88a491ac05a17b662ace833df1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614453"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="bafeb-102">ISymUnmanagedDispose::Destroy 方法</span><span class="sxs-lookup"><span data-stu-id="bafeb-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="bafeb-103">导致要释放内部的所有引用和任何后续方法调用上返回失败的基础对象。</span><span class="sxs-lookup"><span data-stu-id="bafeb-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bafeb-104">语法</span><span class="sxs-lookup"><span data-stu-id="bafeb-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bafeb-105">返回值</span><span class="sxs-lookup"><span data-stu-id="bafeb-105">Return Value</span></span>  
 <span data-ttu-id="bafeb-106">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="bafeb-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bafeb-107">要求</span><span class="sxs-lookup"><span data-stu-id="bafeb-107">Requirements</span></span>  
 <span data-ttu-id="bafeb-108">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bafeb-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafeb-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="bafeb-109">See also</span></span>
- [<span data-ttu-id="bafeb-110">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="bafeb-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
