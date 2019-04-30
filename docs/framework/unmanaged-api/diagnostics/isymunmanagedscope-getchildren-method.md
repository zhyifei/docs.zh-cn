---
title: ISymUnmanagedScope::GetChildren 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3cad217ddf2d5354ad019f26fd10fb9ccd004d61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986191"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="33e82-102">ISymUnmanagedScope::GetChildren 方法</span><span class="sxs-lookup"><span data-stu-id="33e82-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="33e82-103">获取此作用域的子级。</span><span class="sxs-lookup"><span data-stu-id="33e82-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e82-104">语法</span><span class="sxs-lookup"><span data-stu-id="33e82-104">Syntax</span></span>  
  
```  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33e82-105">参数</span><span class="sxs-lookup"><span data-stu-id="33e82-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="33e82-106">[in]一个`ULONG32`指示的大小`children`数组。</span><span class="sxs-lookup"><span data-stu-id="33e82-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="33e82-107">[out]一个指向`ULONG32`接收包含子级所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="33e82-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="33e82-108">[out]返回的子级的数组。</span><span class="sxs-lookup"><span data-stu-id="33e82-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33e82-109">返回值</span><span class="sxs-lookup"><span data-stu-id="33e82-109">Return Value</span></span>  
 <span data-ttu-id="33e82-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="33e82-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33e82-111">要求</span><span class="sxs-lookup"><span data-stu-id="33e82-111">Requirements</span></span>  
 <span data-ttu-id="33e82-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="33e82-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e82-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="33e82-113">See also</span></span>

- [<span data-ttu-id="33e82-114">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="33e82-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="33e82-115">GetParent 方法</span><span class="sxs-lookup"><span data-stu-id="33e82-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
