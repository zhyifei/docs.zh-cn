---
title: ISymUnmanagedDocument::GetDocumentType 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adad8854052d76476076e5e1357f6d3e2dec1052
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629470"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="ab337-102">ISymUnmanagedDocument::GetDocumentType 方法</span><span class="sxs-lookup"><span data-stu-id="ab337-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="ab337-103">获取此文档的文档类型。</span><span class="sxs-lookup"><span data-stu-id="ab337-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab337-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab337-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab337-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab337-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ab337-106">[out]指向一个变量来接收文档类型的指针。</span><span class="sxs-lookup"><span data-stu-id="ab337-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab337-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ab337-107">Return Value</span></span>  
 <span data-ttu-id="ab337-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ab337-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab337-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab337-109">See also</span></span>
- [<span data-ttu-id="ab337-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="ab337-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
