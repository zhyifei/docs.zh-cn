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
ms.openlocfilehash: c786cd43a25aa0c69c19e57452a3b190c7bfb167
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426836"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="2baec-102">ISymUnmanagedScope::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="2baec-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="2baec-103">获取在此作用域中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="2baec-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2baec-104">语法</span><span class="sxs-lookup"><span data-stu-id="2baec-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2baec-105">参数</span><span class="sxs-lookup"><span data-stu-id="2baec-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="2baec-106">[in] `namespaces` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="2baec-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="2baec-107">[out]指向的指针`ULONG32`接收包含命名空间所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="2baec-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="2baec-108">[out]接收这些命名空间数组。</span><span class="sxs-lookup"><span data-stu-id="2baec-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2baec-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2baec-109">Return Value</span></span>  
 <span data-ttu-id="2baec-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="2baec-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2baec-111">要求</span><span class="sxs-lookup"><span data-stu-id="2baec-111">Requirements</span></span>  
 <span data-ttu-id="2baec-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2baec-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2baec-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2baec-113">See Also</span></span>  
 [<span data-ttu-id="2baec-114">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="2baec-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
