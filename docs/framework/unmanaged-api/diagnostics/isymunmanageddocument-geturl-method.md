---
title: ISymUnmanagedDocument::GetURL 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a93ef073d4dd2eaf58c057d4cdf25fa39082e14
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706321"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="f96aa-102">ISymUnmanagedDocument::GetURL 方法</span><span class="sxs-lookup"><span data-stu-id="f96aa-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="f96aa-103">返回此文档的统一资源定位符 (URL)。</span><span class="sxs-lookup"><span data-stu-id="f96aa-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f96aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="f96aa-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f96aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="f96aa-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="f96aa-106">[in]大小，以字符为单位的`szURL`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f96aa-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="f96aa-107">[out]指向一个变量来接收 URL，包括 null 终止的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="f96aa-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="f96aa-108">[out]包含 URL 的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f96aa-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f96aa-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f96aa-109">Return Value</span></span>  
 <span data-ttu-id="f96aa-110">如果方法成功，则为 S_OK否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="f96aa-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f96aa-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f96aa-111">See also</span></span>
- [<span data-ttu-id="f96aa-112">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="f96aa-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
