---
title: ISymUnmanagedNamespace::GetNamespaces 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 039dab1b4ca86cb26de739e74b152f108f074c43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426167"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="e93e7-102">ISymUnmanagedNamespace::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="e93e7-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="e93e7-103">获取此命名空间的子级。</span><span class="sxs-lookup"><span data-stu-id="e93e7-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e93e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="e93e7-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e93e7-105">参数</span><span class="sxs-lookup"><span data-stu-id="e93e7-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="e93e7-106">[in]A `ULONG32` ，该值指示的大小`namespaces`数组。</span><span class="sxs-lookup"><span data-stu-id="e93e7-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="e93e7-107">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含命名空间所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e93e7-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="e93e7-108">[out]指向包含的命名空间的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="e93e7-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e93e7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e93e7-109">Return Value</span></span>  
 <span data-ttu-id="e93e7-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e93e7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e93e7-111">要求</span><span class="sxs-lookup"><span data-stu-id="e93e7-111">Requirements</span></span>  
 <span data-ttu-id="e93e7-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e93e7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e93e7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e93e7-113">See Also</span></span>  
 [<span data-ttu-id="e93e7-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="e93e7-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
