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
ms.openlocfilehash: bf932b63973f93c56883f099ddaadd9d1519f337
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446328"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="cd03b-102">ISymUnmanagedScope::GetLocals 方法</span><span class="sxs-lookup"><span data-stu-id="cd03b-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="cd03b-103">获取在此范围内定义的局部变量。</span><span class="sxs-lookup"><span data-stu-id="cd03b-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd03b-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd03b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd03b-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd03b-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="cd03b-106">中一个 `ULONG32`，指示 `locals` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="cd03b-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="cd03b-107">弄指向 `ULONG32` 的指针，该指针接收包含本地变量所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="cd03b-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="cd03b-108">弄接收局部变量的数组。</span><span class="sxs-lookup"><span data-stu-id="cd03b-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd03b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="cd03b-109">Return Value</span></span>  
 <span data-ttu-id="cd03b-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="cd03b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd03b-111">要求</span><span class="sxs-lookup"><span data-stu-id="cd03b-111">Requirements</span></span>  
 <span data-ttu-id="cd03b-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="cd03b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd03b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd03b-113">See also</span></span>

- [<span data-ttu-id="cd03b-114">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="cd03b-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
