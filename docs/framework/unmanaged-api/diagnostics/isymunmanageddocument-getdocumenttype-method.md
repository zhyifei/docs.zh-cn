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
ms.openlocfilehash: 5ec69aa06816b117fb05853001e59532629504c4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614599"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="0d102-102">ISymUnmanagedDocument::GetDocumentType 方法</span><span class="sxs-lookup"><span data-stu-id="0d102-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="0d102-103">获取此文档的文档类型。</span><span class="sxs-lookup"><span data-stu-id="0d102-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d102-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d102-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d102-105">参数</span><span class="sxs-lookup"><span data-stu-id="0d102-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0d102-106">弄指向接收文档类型的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="0d102-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d102-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0d102-107">Return Value</span></span>  
 <span data-ttu-id="0d102-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0d102-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d102-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d102-109">See also</span></span>

- [<span data-ttu-id="0d102-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="0d102-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
