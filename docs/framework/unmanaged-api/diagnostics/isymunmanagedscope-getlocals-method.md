---
title: ISymUnmanagedScope::GetLocals 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e45f5411d48032b86403e35358d7ce83d5f97c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777909"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="c3b30-102">ISymUnmanagedScope::GetLocals 方法</span><span class="sxs-lookup"><span data-stu-id="c3b30-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="c3b30-103">获取此范围内定义的本地变量。</span><span class="sxs-lookup"><span data-stu-id="c3b30-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b30-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3b30-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b30-105">参数</span><span class="sxs-lookup"><span data-stu-id="c3b30-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="c3b30-106">[in]一个`ULONG32`指示的大小`locals`数组。</span><span class="sxs-lookup"><span data-stu-id="c3b30-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="c3b30-107">[out]一个指向`ULONG32`接收包含本地变量所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="c3b30-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="c3b30-108">[out]接收本地变量的数组。</span><span class="sxs-lookup"><span data-stu-id="c3b30-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3b30-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c3b30-109">Return Value</span></span>  
 <span data-ttu-id="c3b30-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c3b30-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b30-111">要求</span><span class="sxs-lookup"><span data-stu-id="c3b30-111">Requirements</span></span>  
 <span data-ttu-id="c3b30-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c3b30-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b30-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3b30-113">See also</span></span>

- [<span data-ttu-id="c3b30-114">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="c3b30-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
