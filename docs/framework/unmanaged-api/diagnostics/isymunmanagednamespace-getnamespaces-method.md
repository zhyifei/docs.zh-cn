---
title: "ISymUnmanagedNamespace::GetNamespaces 方法"
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
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69ee0f6385abf78a368d488d0190796516c4f3d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="e763a-102">ISymUnmanagedNamespace::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="e763a-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="e763a-103">获取此命名空间的子级。</span><span class="sxs-lookup"><span data-stu-id="e763a-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e763a-104">语法</span><span class="sxs-lookup"><span data-stu-id="e763a-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e763a-105">参数</span><span class="sxs-lookup"><span data-stu-id="e763a-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="e763a-106">[in]A `ULONG32` ，该值指示的大小`namespaces`数组。</span><span class="sxs-lookup"><span data-stu-id="e763a-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="e763a-107">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含命名空间所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e763a-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="e763a-108">[out]指向包含的命名空间的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="e763a-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e763a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e763a-109">Return Value</span></span>  
 <span data-ttu-id="e763a-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e763a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e763a-111">惠?</span><span class="sxs-lookup"><span data-stu-id="e763a-111">Requirements</span></span>  
 <span data-ttu-id="e763a-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e763a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e763a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e763a-113">See Also</span></span>  
 [<span data-ttu-id="e763a-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="e763a-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
