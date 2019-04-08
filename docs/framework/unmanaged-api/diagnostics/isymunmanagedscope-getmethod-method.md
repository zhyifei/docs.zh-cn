---
title: ISymUnmanagedScope::GetMethod 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 954b1d91f33fe9a7e4df1ef51ee3666047836a17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099958"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="e9451-102">ISymUnmanagedScope::GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="e9451-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="e9451-103">获取包含此作用域的方法。</span><span class="sxs-lookup"><span data-stu-id="e9451-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9451-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9451-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9451-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9451-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e9451-106">[out]指向返回的指针[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e9451-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9451-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e9451-107">Return Value</span></span>  
 <span data-ttu-id="e9451-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e9451-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9451-109">要求</span><span class="sxs-lookup"><span data-stu-id="e9451-109">Requirements</span></span>  
 <span data-ttu-id="e9451-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e9451-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9451-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9451-111">See also</span></span>

- [<span data-ttu-id="e9451-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="e9451-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
