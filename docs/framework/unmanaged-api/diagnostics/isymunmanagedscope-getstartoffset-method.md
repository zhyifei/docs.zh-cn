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
ms.openlocfilehash: 071ad6c24804eecb0f2260d54c854f22ff997bc1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611011"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="bd153-102">ISymUnmanagedScope::GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="bd153-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="bd153-103">获取此范围的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="bd153-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd153-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd153-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd153-105">参数</span><span class="sxs-lookup"><span data-stu-id="bd153-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bd153-106">弄指向的指针 `ULONG32` ，该指针包含起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="bd153-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd153-107">返回值</span><span class="sxs-lookup"><span data-stu-id="bd153-107">Return Value</span></span>  
 <span data-ttu-id="bd153-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="bd153-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd153-109">要求</span><span class="sxs-lookup"><span data-stu-id="bd153-109">Requirements</span></span>  
 <span data-ttu-id="bd153-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="bd153-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd153-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd153-111">See also</span></span>

- [<span data-ttu-id="bd153-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="bd153-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="bd153-113">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="bd153-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
