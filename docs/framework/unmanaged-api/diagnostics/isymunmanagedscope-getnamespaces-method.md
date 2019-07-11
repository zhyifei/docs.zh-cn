---
title: ISymUnmanagedScope::GetNamespaces 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d2c64d7ead2f7ce3d76b40f4fdc604506ee85561
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777890"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="664fe-102">ISymUnmanagedScope::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="664fe-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="664fe-103">获取此范围内所使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="664fe-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="664fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="664fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="664fe-105">参数</span><span class="sxs-lookup"><span data-stu-id="664fe-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="664fe-106">[in] `namespaces` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="664fe-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="664fe-107">[out]一个指向`ULONG32`接收包含命名空间所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="664fe-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="664fe-108">[out]接收这些命名空间数组。</span><span class="sxs-lookup"><span data-stu-id="664fe-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="664fe-109">返回值</span><span class="sxs-lookup"><span data-stu-id="664fe-109">Return Value</span></span>  
 <span data-ttu-id="664fe-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="664fe-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="664fe-111">要求</span><span class="sxs-lookup"><span data-stu-id="664fe-111">Requirements</span></span>  
 <span data-ttu-id="664fe-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="664fe-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="664fe-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="664fe-113">See also</span></span>

- [<span data-ttu-id="664fe-114">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="664fe-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
