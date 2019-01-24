---
title: ISymUnmanagedMethod::GetRootScope 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 458f6ab4a6848ce6921542ca62fe6d5c7cf4719f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704636"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="b5a38-102">ISymUnmanagedMethod::GetRootScope 方法</span><span class="sxs-lookup"><span data-stu-id="b5a38-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="b5a38-103">获取在此方法内的根词法范围。</span><span class="sxs-lookup"><span data-stu-id="b5a38-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="b5a38-104">此范围包括整个方法。</span><span class="sxs-lookup"><span data-stu-id="b5a38-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5a38-105">语法</span><span class="sxs-lookup"><span data-stu-id="b5a38-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5a38-106">参数</span><span class="sxs-lookup"><span data-stu-id="b5a38-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b5a38-107">[out]一个指针，它设置为返回[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b5a38-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5a38-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b5a38-108">Return Value</span></span>  
 <span data-ttu-id="b5a38-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="b5a38-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5a38-110">要求</span><span class="sxs-lookup"><span data-stu-id="b5a38-110">Requirements</span></span>  
 <span data-ttu-id="b5a38-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b5a38-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a38-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5a38-112">See also</span></span>
- [<span data-ttu-id="b5a38-113">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="b5a38-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
