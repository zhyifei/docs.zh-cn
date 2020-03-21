---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 97f0d81c389ffd0bd8a69df2ca39322d726f98bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176625"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="f9a71-102">ISymENCUnmanagedMethod::GetDocumentsForMethod 方法</span><span class="sxs-lookup"><span data-stu-id="f9a71-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="f9a71-103">获取此方法中具有行的文档。</span><span class="sxs-lookup"><span data-stu-id="f9a71-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a71-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9a71-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9a71-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f9a71-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="f9a71-106">[在]指向 的缓冲区的长度`pcDocs`。</span><span class="sxs-lookup"><span data-stu-id="f9a71-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="f9a71-107">[出]指向 的指针`ULONG32`，该指针接收包含文档所需的缓冲区的大小（以字符表示）。</span><span class="sxs-lookup"><span data-stu-id="f9a71-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="f9a71-108">[在]包含文档的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f9a71-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9a71-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f9a71-109">Return Value</span></span>  
 <span data-ttu-id="f9a71-110">如果方法成功，S_OK;否则，错误代码。</span><span class="sxs-lookup"><span data-stu-id="f9a71-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9a71-111">要求</span><span class="sxs-lookup"><span data-stu-id="f9a71-111">Requirements</span></span>  
 <span data-ttu-id="f9a71-112">**标题：** 科西姆.伊德尔，科西姆.h</span><span class="sxs-lookup"><span data-stu-id="f9a71-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a71-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9a71-113">See also</span></span>

- [<span data-ttu-id="f9a71-114">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="f9a71-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
