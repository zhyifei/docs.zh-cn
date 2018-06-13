---
title: ISymUnmanagedDocument::FindClosestLine 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f31dad53f42fdd8f7ac3a0cb995b507ecc3590d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424438"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="b0853-102">ISymUnmanagedDocument::FindClosestLine 方法</span><span class="sxs-lookup"><span data-stu-id="b0853-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="b0853-103">是作为序列点的最近的一行中一行返回此文档中可能也可能不是序列点。</span><span class="sxs-lookup"><span data-stu-id="b0853-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0853-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0853-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0853-105">参数</span><span class="sxs-lookup"><span data-stu-id="b0853-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="b0853-106">[in]本文档中的行。</span><span class="sxs-lookup"><span data-stu-id="b0853-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b0853-107">[out]指向接收行的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="b0853-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0853-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b0853-108">Return Value</span></span>  
 <span data-ttu-id="b0853-109">如果该方法成功; 则为 S_OK否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="b0853-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0853-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0853-110">See Also</span></span>  
 [<span data-ttu-id="b0853-111">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="b0853-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
