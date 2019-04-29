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
ms.openlocfilehash: 05ce47953358b7025e30080fbbaf288a6c0e879d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939836"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="16610-102">ISymUnmanagedDocument::GetLanguage 方法</span><span class="sxs-lookup"><span data-stu-id="16610-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="16610-103">获取此文档的语言标识符</span><span class="sxs-lookup"><span data-stu-id="16610-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16610-104">语法</span><span class="sxs-lookup"><span data-stu-id="16610-104">Syntax</span></span>  
  
```  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16610-105">参数</span><span class="sxs-lookup"><span data-stu-id="16610-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="16610-106">[out]指向一个变量来接收语言标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="16610-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16610-107">返回值</span><span class="sxs-lookup"><span data-stu-id="16610-107">Return Value</span></span>  
 <span data-ttu-id="16610-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="16610-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16610-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="16610-109">See also</span></span>

- [<span data-ttu-id="16610-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="16610-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
