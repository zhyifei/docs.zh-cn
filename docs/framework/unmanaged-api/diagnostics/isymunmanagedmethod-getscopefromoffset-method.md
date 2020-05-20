---
title: ISymUnmanagedMethod::GetScopeFromOffset 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: 4eefd019280f501a6ce194e5ce84388e32cc66e1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615132"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="fefd8-102">ISymUnmanagedMethod::GetScopeFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="fefd8-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="fefd8-103">获取此方法内包含给定偏移量的最封闭的词法范围。</span><span class="sxs-lookup"><span data-stu-id="fefd8-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="fefd8-104">这可用于启动本地变量搜索。</span><span class="sxs-lookup"><span data-stu-id="fefd8-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fefd8-105">语法</span><span class="sxs-lookup"><span data-stu-id="fefd8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fefd8-106">参数</span><span class="sxs-lookup"><span data-stu-id="fefd8-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="fefd8-107">中一个 `ULONG` 包含偏移量的。</span><span class="sxs-lookup"><span data-stu-id="fefd8-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fefd8-108">弄设置为返回的[ISymUnmanagedScope](isymunmanagedscope-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="fefd8-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fefd8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fefd8-109">Return Value</span></span>  
 <span data-ttu-id="fefd8-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="fefd8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fefd8-111">要求</span><span class="sxs-lookup"><span data-stu-id="fefd8-111">Requirements</span></span>  
 <span data-ttu-id="fefd8-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="fefd8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fefd8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fefd8-113">See also</span></span>

- [<span data-ttu-id="fefd8-114">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="fefd8-114">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
