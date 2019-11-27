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
ms.openlocfilehash: c7e9d2fe94c33127d8b105333ad6dac9d6cc5af6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446370"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="5a718-102">ISymUnmanagedScope::GetChildren 方法</span><span class="sxs-lookup"><span data-stu-id="5a718-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="5a718-103">获取此作用域的子级。</span><span class="sxs-lookup"><span data-stu-id="5a718-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a718-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a718-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a718-105">参数</span><span class="sxs-lookup"><span data-stu-id="5a718-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="5a718-106">中一个 `ULONG32`，指示 `children` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="5a718-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="5a718-107">弄指向 `ULONG32` 的指针，该指针接收包含子级所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="5a718-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="5a718-108">弄返回的子元素数组。</span><span class="sxs-lookup"><span data-stu-id="5a718-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a718-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5a718-109">Return Value</span></span>  
 <span data-ttu-id="5a718-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="5a718-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a718-111">要求</span><span class="sxs-lookup"><span data-stu-id="5a718-111">Requirements</span></span>  
 <span data-ttu-id="5a718-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="5a718-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a718-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a718-113">See also</span></span>

- [<span data-ttu-id="5a718-114">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="5a718-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="5a718-115">GetParent 方法</span><span class="sxs-lookup"><span data-stu-id="5a718-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
