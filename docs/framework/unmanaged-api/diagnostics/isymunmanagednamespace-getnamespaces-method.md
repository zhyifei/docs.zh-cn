---
title: "ISymUnmanagedNamespace::GetNamespaces 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetNamespaces
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ef84358443520aa0548ef2244c2537b7a593f9e3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="f4c66-102">ISymUnmanagedNamespace::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="f4c66-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="f4c66-103">获取此命名空间的子级。</span><span class="sxs-lookup"><span data-stu-id="f4c66-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4c66-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4c66-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4c66-105">参数</span><span class="sxs-lookup"><span data-stu-id="f4c66-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="f4c66-106">[in]A `ULONG32` ，该值指示的大小`namespaces`数组。</span><span class="sxs-lookup"><span data-stu-id="f4c66-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="f4c66-107">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含命名空间所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f4c66-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="f4c66-108">[out]指向包含的命名空间的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="f4c66-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4c66-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f4c66-109">Return Value</span></span>  
 <span data-ttu-id="f4c66-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="f4c66-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4c66-111">要求</span><span class="sxs-lookup"><span data-stu-id="f4c66-111">Requirements</span></span>  
 <span data-ttu-id="f4c66-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f4c66-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c66-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4c66-113">See Also</span></span>  
 [<span data-ttu-id="f4c66-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="f4c66-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
