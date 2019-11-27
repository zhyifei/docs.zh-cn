---
title: ISymUnmanagedScope::GetStartOffset 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
ms.openlocfilehash: 9d1ee82f24e1908af1998e424006415af3134456
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446283"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="7a39f-102">ISymUnmanagedScope::GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="7a39f-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="7a39f-103">获取此范围的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="7a39f-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a39f-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a39f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a39f-105">参数</span><span class="sxs-lookup"><span data-stu-id="7a39f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7a39f-106">弄指向包含起始偏移量的 `ULONG32` 的指针。</span><span class="sxs-lookup"><span data-stu-id="7a39f-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a39f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7a39f-107">Return Value</span></span>  
 <span data-ttu-id="7a39f-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="7a39f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a39f-109">要求</span><span class="sxs-lookup"><span data-stu-id="7a39f-109">Requirements</span></span>  
 <span data-ttu-id="7a39f-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="7a39f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a39f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a39f-111">See also</span></span>

- [<span data-ttu-id="7a39f-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="7a39f-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="7a39f-113">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="7a39f-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
