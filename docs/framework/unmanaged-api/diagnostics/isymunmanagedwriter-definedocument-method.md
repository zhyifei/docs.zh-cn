---
title: "ISymUnmanagedWriter::DefineDocument 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 638759cb52eb28cc79217da81a867f2593e1ae97
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="c667d-102">ISymUnmanagedWriter::DefineDocument 方法</span><span class="sxs-lookup"><span data-stu-id="c667d-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="c667d-103">定义源文档。</span><span class="sxs-lookup"><span data-stu-id="c667d-103">Defines a source document.</span></span> <span data-ttu-id="c667d-104">Guid 提供已知的语言、 供应商和文档类型。</span><span class="sxs-lookup"><span data-stu-id="c667d-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c667d-105">语法</span><span class="sxs-lookup"><span data-stu-id="c667d-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c667d-106">参数</span><span class="sxs-lookup"><span data-stu-id="c667d-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="c667d-107">[in]指向的指针`WCHAR`定义标识文档的统一资源定位符 (URL)。</span><span class="sxs-lookup"><span data-stu-id="c667d-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="c667d-108">[in]指向定义文档语言的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="c667d-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="c667d-109">[in]指向定义文档语言的供应商的标识的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="c667d-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="c667d-110">[in]指向一个定义的文档类型的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="c667d-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c667d-111">[out]指向返回的指针[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c667d-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c667d-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c667d-112">Return Value</span></span>  
 <span data-ttu-id="c667d-113">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c667d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c667d-114">要求</span><span class="sxs-lookup"><span data-stu-id="c667d-114">Requirements</span></span>  
 <span data-ttu-id="c667d-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c667d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c667d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c667d-116">See Also</span></span>  
 [<span data-ttu-id="c667d-117">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="c667d-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
