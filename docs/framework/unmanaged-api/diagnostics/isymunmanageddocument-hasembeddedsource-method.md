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
ms.openlocfilehash: 533d8a5481fe9ba7e7e65775229156a9cc3cf4d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449106"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="86fa8-102">ISymUnmanagedDocument::HasEmbeddedSource 方法</span><span class="sxs-lookup"><span data-stu-id="86fa8-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="86fa8-103">如果文档在调试符号中嵌入了源，则返回 `true`;否则，将返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="86fa8-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86fa8-104">语法</span><span class="sxs-lookup"><span data-stu-id="86fa8-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86fa8-105">参数</span><span class="sxs-lookup"><span data-stu-id="86fa8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="86fa8-106">弄指向一个变量的指针，该变量指示文档是否将源嵌入调试符号。</span><span class="sxs-lookup"><span data-stu-id="86fa8-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86fa8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="86fa8-107">Return Value</span></span>  
 <span data-ttu-id="86fa8-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="86fa8-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86fa8-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86fa8-109">See also</span></span>

- [<span data-ttu-id="86fa8-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="86fa8-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
