---
title: ISymUnmanagedDocument::GetLanguage 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 186ea5fd46ca5c6205ff1f98d8964e656655a2ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666028"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="6a912-102">ISymUnmanagedDocument::GetLanguage 方法</span><span class="sxs-lookup"><span data-stu-id="6a912-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="6a912-103">获取此文档的语言标识符</span><span class="sxs-lookup"><span data-stu-id="6a912-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a912-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a912-104">Syntax</span></span>  
  
```  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a912-105">参数</span><span class="sxs-lookup"><span data-stu-id="6a912-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6a912-106">[out]指向一个变量来接收语言标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="6a912-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a912-107">返回值</span><span class="sxs-lookup"><span data-stu-id="6a912-107">Return Value</span></span>  
 <span data-ttu-id="6a912-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="6a912-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a912-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a912-109">See also</span></span>
- [<span data-ttu-id="6a912-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="6a912-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
