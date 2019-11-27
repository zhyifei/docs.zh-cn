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
ms.openlocfilehash: 36b1b2394907f242c0e8c5e277c0d1c5b3b02e1b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448898"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="4fc06-102">ISymUnmanagedMethod::GetScopeFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="4fc06-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="4fc06-103">获取此方法内包含给定偏移量的最封闭的词法范围。</span><span class="sxs-lookup"><span data-stu-id="4fc06-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="4fc06-104">这可用于启动本地变量搜索。</span><span class="sxs-lookup"><span data-stu-id="4fc06-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc06-105">语法</span><span class="sxs-lookup"><span data-stu-id="4fc06-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fc06-106">参数</span><span class="sxs-lookup"><span data-stu-id="4fc06-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="4fc06-107">中一个包含偏移量的 `ULONG`。</span><span class="sxs-lookup"><span data-stu-id="4fc06-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="4fc06-108">弄设置为返回的[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="4fc06-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fc06-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4fc06-109">Return Value</span></span>  
 <span data-ttu-id="4fc06-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="4fc06-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fc06-111">要求</span><span class="sxs-lookup"><span data-stu-id="4fc06-111">Requirements</span></span>  
 <span data-ttu-id="4fc06-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="4fc06-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc06-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fc06-113">See also</span></span>

- [<span data-ttu-id="4fc06-114">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="4fc06-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
