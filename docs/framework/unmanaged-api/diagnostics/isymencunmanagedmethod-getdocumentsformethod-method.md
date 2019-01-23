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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd294037774721839b0c4f1f09bdc2a6e3b87841
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562669"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="2e8d7-102">ISymENCUnmanagedMethod::GetDocumentsForMethod 方法</span><span class="sxs-lookup"><span data-stu-id="2e8d7-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="2e8d7-103">获取此方法中的行的文档。</span><span class="sxs-lookup"><span data-stu-id="2e8d7-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e8d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e8d7-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e8d7-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e8d7-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="2e8d7-106">[in]指向缓冲区的长度`pcDocs`。</span><span class="sxs-lookup"><span data-stu-id="2e8d7-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="2e8d7-107">[out]一个指向`ULONG32`用于接收大小，以字符为单位，包含文档所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2e8d7-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="2e8d7-108">[in]包含文档的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2e8d7-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e8d7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2e8d7-109">Return Value</span></span>  
 <span data-ttu-id="2e8d7-110">如果方法成功，则为 S_OK否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="2e8d7-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e8d7-111">要求</span><span class="sxs-lookup"><span data-stu-id="2e8d7-111">Requirements</span></span>  
 <span data-ttu-id="2e8d7-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2e8d7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e8d7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e8d7-113">See also</span></span>
- [<span data-ttu-id="2e8d7-114">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="2e8d7-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
