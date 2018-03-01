---
title: "ISymENCUnmanagedMethod::GetSourceExtentInDocument 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6116ee89cb643cc0010ef2c8a463fa131777584e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="a6867-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="a6867-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="a6867-103">获取最小值中特定文档开始行和方法的最大结束行。</span><span class="sxs-lookup"><span data-stu-id="a6867-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6867-104">语法</span><span class="sxs-lookup"><span data-stu-id="a6867-104">Syntax</span></span>  
  
```  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6867-105">参数</span><span class="sxs-lookup"><span data-stu-id="a6867-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="a6867-106">[in]指向文档的指针。</span><span class="sxs-lookup"><span data-stu-id="a6867-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="a6867-107">[out]指向的指针`ULONG32`接收的起始行。</span><span class="sxs-lookup"><span data-stu-id="a6867-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="a6867-108">[out]指向的指针`ULONG32`接收结束行。</span><span class="sxs-lookup"><span data-stu-id="a6867-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6867-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a6867-109">Return Value</span></span>  
 <span data-ttu-id="a6867-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="a6867-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6867-111">惠?</span><span class="sxs-lookup"><span data-stu-id="a6867-111">Requirements</span></span>  
 <span data-ttu-id="a6867-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a6867-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6867-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6867-113">See Also</span></span>  
 [<span data-ttu-id="a6867-114">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="a6867-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
