---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f29111fd68d9a47cd90687cc6aa2743968e727d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484597"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="7348a-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="7348a-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="7348a-103">获取的最小起始行和方法的最大结束行中特定文档。</span><span class="sxs-lookup"><span data-stu-id="7348a-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7348a-104">语法</span><span class="sxs-lookup"><span data-stu-id="7348a-104">Syntax</span></span>  
  
```  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7348a-105">参数</span><span class="sxs-lookup"><span data-stu-id="7348a-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="7348a-106">[in]指向文档的指针。</span><span class="sxs-lookup"><span data-stu-id="7348a-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="7348a-107">[out]一个指向`ULONG32`，它接收的起始行。</span><span class="sxs-lookup"><span data-stu-id="7348a-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="7348a-108">[out]一个指向`ULONG32`接收结束行。</span><span class="sxs-lookup"><span data-stu-id="7348a-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7348a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7348a-109">Return Value</span></span>  
 <span data-ttu-id="7348a-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="7348a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7348a-111">要求</span><span class="sxs-lookup"><span data-stu-id="7348a-111">Requirements</span></span>  
 <span data-ttu-id="7348a-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7348a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7348a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7348a-113">See also</span></span>
- [<span data-ttu-id="7348a-114">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="7348a-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
