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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d34bcaf1ef00806e3883996804336bd22b9b634f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777853"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="bc29e-102">ISymUnmanagedScope::GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="bc29e-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="bc29e-103">获取此范围的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="bc29e-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc29e-104">语法</span><span class="sxs-lookup"><span data-stu-id="bc29e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc29e-105">参数</span><span class="sxs-lookup"><span data-stu-id="bc29e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bc29e-106">[out]一个指向`ULONG32`，其中包含的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="bc29e-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc29e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="bc29e-107">Return Value</span></span>  
 <span data-ttu-id="bc29e-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="bc29e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc29e-109">要求</span><span class="sxs-lookup"><span data-stu-id="bc29e-109">Requirements</span></span>  
 <span data-ttu-id="bc29e-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bc29e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc29e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc29e-111">See also</span></span>

- [<span data-ttu-id="bc29e-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="bc29e-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="bc29e-113">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="bc29e-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
