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
ms.openlocfilehash: 3d7ac84971f7d0e97f7ccd26710151d1aeefe729
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207209"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="9b56a-102">ISymUnmanagedNamespace::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="9b56a-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="9b56a-103">获取此命名空间的子级。</span><span class="sxs-lookup"><span data-stu-id="9b56a-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b56a-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b56a-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b56a-105">参数</span><span class="sxs-lookup"><span data-stu-id="9b56a-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="9b56a-106">[in]一个`ULONG32`指示的大小`namespaces`数组。</span><span class="sxs-lookup"><span data-stu-id="9b56a-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="9b56a-107">[out]一个指向`ULONG32`用于接收大小，以字符为单位，包含命名空间所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="9b56a-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="9b56a-108">[out]指向包含的命名空间的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="9b56a-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b56a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9b56a-109">Return Value</span></span>  
 <span data-ttu-id="9b56a-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="9b56a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b56a-111">要求</span><span class="sxs-lookup"><span data-stu-id="9b56a-111">Requirements</span></span>  
 <span data-ttu-id="9b56a-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9b56a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b56a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b56a-113">See also</span></span>

- [<span data-ttu-id="9b56a-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="9b56a-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
