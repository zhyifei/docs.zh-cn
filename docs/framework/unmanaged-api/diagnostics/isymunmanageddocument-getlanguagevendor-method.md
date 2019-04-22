---
title: ISymUnmanagedDocument::GetLanguageVendor 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd01dcbd45ecae84ccccffb510c20f580ae8c598
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080804"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="a86ac-102">ISymUnmanagedDocument::GetLanguageVendor 方法</span><span class="sxs-lookup"><span data-stu-id="a86ac-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="a86ac-103">获取此文档的语言供应商。</span><span class="sxs-lookup"><span data-stu-id="a86ac-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a86ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="a86ac-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a86ac-105">参数</span><span class="sxs-lookup"><span data-stu-id="a86ac-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a86ac-106">[out]指向一个变量来接收的语言供应商的指针。</span><span class="sxs-lookup"><span data-stu-id="a86ac-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a86ac-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a86ac-107">Return Value</span></span>  
 <span data-ttu-id="a86ac-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="a86ac-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a86ac-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a86ac-109">See also</span></span>

- [<span data-ttu-id="a86ac-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="a86ac-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
