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
ms.openlocfilehash: db119a94cb7df29697836ffda240c29a86922d60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214768"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="cb9f4-102">ISymENCUnmanagedMethod::GetDocumentsForMethod 方法</span><span class="sxs-lookup"><span data-stu-id="cb9f4-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="cb9f4-103">获取此方法中的行的文档。</span><span class="sxs-lookup"><span data-stu-id="cb9f4-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb9f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb9f4-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb9f4-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb9f4-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="cb9f4-106">[in]指向缓冲区的长度`pcDocs`。</span><span class="sxs-lookup"><span data-stu-id="cb9f4-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="cb9f4-107">[out]一个指向`ULONG32`用于接收大小，以字符为单位，包含文档所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="cb9f4-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="cb9f4-108">[in]包含文档的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="cb9f4-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb9f4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="cb9f4-109">Return Value</span></span>  
 <span data-ttu-id="cb9f4-110">如果方法成功，则为 S_OK否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="cb9f4-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb9f4-111">要求</span><span class="sxs-lookup"><span data-stu-id="cb9f4-111">Requirements</span></span>  
 <span data-ttu-id="cb9f4-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cb9f4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb9f4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb9f4-113">See also</span></span>

- [<span data-ttu-id="cb9f4-114">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="cb9f4-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
