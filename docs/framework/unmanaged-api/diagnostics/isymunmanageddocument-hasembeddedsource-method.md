---
title: "ISymUnmanagedDocument::HasEmbeddedSource 方法"
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
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2a903974ac5ac4182bb6fa1664d0c5954cefdb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="9ad85-102">ISymUnmanagedDocument::HasEmbeddedSource 方法</span><span class="sxs-lookup"><span data-stu-id="9ad85-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="9ad85-103">返回`true`如果该文档具有源嵌入在调试符号; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="9ad85-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ad85-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ad85-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ad85-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ad85-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="9ad85-106">[out]指向指示文档是否具有嵌入的调试符号中的源的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="9ad85-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ad85-107">返回值</span><span class="sxs-lookup"><span data-stu-id="9ad85-107">Return Value</span></span>  
 <span data-ttu-id="9ad85-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="9ad85-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad85-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ad85-109">See Also</span></span>  
 [<span data-ttu-id="9ad85-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="9ad85-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
