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
ms.openlocfilehash: 9e6134d39096c4ab157aa545646d83339f92a0b8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441027"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="be534-102">ISymUnmanagedDocument::FindClosestLine 方法</span><span class="sxs-lookup"><span data-stu-id="be534-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="be534-103">如果此文档中的一行可能是也可能不是序列点，则返回作为序列点的最近行。</span><span class="sxs-lookup"><span data-stu-id="be534-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be534-104">语法</span><span class="sxs-lookup"><span data-stu-id="be534-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be534-105">参数</span><span class="sxs-lookup"><span data-stu-id="be534-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="be534-106">中此文档中的一行。</span><span class="sxs-lookup"><span data-stu-id="be534-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="be534-107">弄指向接收行的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="be534-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be534-108">返回值</span><span class="sxs-lookup"><span data-stu-id="be534-108">Return Value</span></span>  
 <span data-ttu-id="be534-109">如果该方法成功，则 S_OK;否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="be534-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be534-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be534-110">See also</span></span>

- [<span data-ttu-id="be534-111">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="be534-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
