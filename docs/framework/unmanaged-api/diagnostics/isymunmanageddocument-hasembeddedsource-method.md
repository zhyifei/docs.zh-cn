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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094263"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="ce10e-102">ISymUnmanagedDocument::HasEmbeddedSource 方法</span><span class="sxs-lookup"><span data-stu-id="ce10e-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="ce10e-103">返回`true`如果该文档具有源嵌入在调试的符号; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="ce10e-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce10e-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce10e-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce10e-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce10e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ce10e-106">[out]指向指示文档是否具有源嵌入在调试符号的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="ce10e-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce10e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ce10e-107">Return Value</span></span>  
 <span data-ttu-id="ce10e-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ce10e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce10e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce10e-109">See also</span></span>

- [<span data-ttu-id="ce10e-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="ce10e-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
