---
title: "ISymUnmanagedDocument::GetDocumentType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetDocumentType
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b6e2d81680c2aa5973c0095a6a3ba7cfa158031
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="4e350-102">ISymUnmanagedDocument::GetDocumentType 方法</span><span class="sxs-lookup"><span data-stu-id="4e350-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="4e350-103">获取此文档的文档类型。</span><span class="sxs-lookup"><span data-stu-id="4e350-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e350-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e350-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e350-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e350-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4e350-106">[out]指向接收文档类型的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="4e350-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e350-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4e350-107">Return Value</span></span>  
 <span data-ttu-id="4e350-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="4e350-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e350-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e350-109">See Also</span></span>  
 [<span data-ttu-id="4e350-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="4e350-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
