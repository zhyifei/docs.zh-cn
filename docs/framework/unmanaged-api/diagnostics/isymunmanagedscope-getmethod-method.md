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
ms.openlocfilehash: ebef54baf4e560b364845a521e4b4444ed359395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426115"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="49529-102">ISymUnmanagedScope::GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="49529-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="49529-103">获取包含此作用域的方法。</span><span class="sxs-lookup"><span data-stu-id="49529-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49529-104">语法</span><span class="sxs-lookup"><span data-stu-id="49529-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49529-105">参数</span><span class="sxs-lookup"><span data-stu-id="49529-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="49529-106">[out]指向返回的指针[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="49529-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49529-107">返回值</span><span class="sxs-lookup"><span data-stu-id="49529-107">Return Value</span></span>  
 <span data-ttu-id="49529-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="49529-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49529-109">要求</span><span class="sxs-lookup"><span data-stu-id="49529-109">Requirements</span></span>  
 <span data-ttu-id="49529-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="49529-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49529-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="49529-111">See Also</span></span>  
 [<span data-ttu-id="49529-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="49529-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
