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
ms.openlocfilehash: ab7df9b77b1820f291c1b1873b4dfb39e326bc34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939927"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="2246e-102">ISymUnmanagedDocument::FindClosestLine 方法</span><span class="sxs-lookup"><span data-stu-id="2246e-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="2246e-103">返回一个序列点，最近的一行，可能也可能不是序列点本文档中提供一条线。</span><span class="sxs-lookup"><span data-stu-id="2246e-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2246e-104">语法</span><span class="sxs-lookup"><span data-stu-id="2246e-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2246e-105">参数</span><span class="sxs-lookup"><span data-stu-id="2246e-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="2246e-106">[in]本文档中的行。</span><span class="sxs-lookup"><span data-stu-id="2246e-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2246e-107">[out]指向一个变量来接收行的指针。</span><span class="sxs-lookup"><span data-stu-id="2246e-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2246e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2246e-108">Return Value</span></span>  
 <span data-ttu-id="2246e-109">如果方法成功，则为 S_OK否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="2246e-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2246e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="2246e-110">See also</span></span>

- [<span data-ttu-id="2246e-111">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="2246e-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
