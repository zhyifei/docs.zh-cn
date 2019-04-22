---
title: ISymUnmanagedDocument::HasEmbeddedSource 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d6c79be95ff80c8de9b07cb33be46a5f5db22b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094263"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="022ba-102">ISymUnmanagedDocument::HasEmbeddedSource 方法</span><span class="sxs-lookup"><span data-stu-id="022ba-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="022ba-103">返回`true`如果该文档具有源嵌入在调试的符号; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="022ba-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="022ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="022ba-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="022ba-105">参数</span><span class="sxs-lookup"><span data-stu-id="022ba-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="022ba-106">[out]指向指示文档是否具有源嵌入在调试符号的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="022ba-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="022ba-107">返回值</span><span class="sxs-lookup"><span data-stu-id="022ba-107">Return Value</span></span>  
 <span data-ttu-id="022ba-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="022ba-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="022ba-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="022ba-109">See also</span></span>

- [<span data-ttu-id="022ba-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="022ba-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
