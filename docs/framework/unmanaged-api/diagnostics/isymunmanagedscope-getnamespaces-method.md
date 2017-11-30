---
title: "ISymUnmanagedScope::GetNamespaces 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetNamespaces
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 641ce6c4587f9f23743a3c1b5a1aeb6fb77edde7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="af471-102">ISymUnmanagedScope::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="af471-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="af471-103">获取在此作用域中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="af471-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af471-104">语法</span><span class="sxs-lookup"><span data-stu-id="af471-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af471-105">参数</span><span class="sxs-lookup"><span data-stu-id="af471-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="af471-106">[in] `namespaces` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="af471-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="af471-107">[out]指向的指针`ULONG32`接收包含命名空间所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="af471-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="af471-108">[out]接收这些命名空间数组。</span><span class="sxs-lookup"><span data-stu-id="af471-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af471-109">返回值</span><span class="sxs-lookup"><span data-stu-id="af471-109">Return Value</span></span>  
 <span data-ttu-id="af471-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="af471-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af471-111">要求</span><span class="sxs-lookup"><span data-stu-id="af471-111">Requirements</span></span>  
 <span data-ttu-id="af471-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="af471-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af471-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af471-113">See Also</span></span>  
 [<span data-ttu-id="af471-114">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="af471-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
