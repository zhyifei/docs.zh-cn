---
title: "ISymUnmanagedDocument::GetLanguageVendor 方法"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc0d05e3d0536f596fc305e32863a39d27a77fe9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="2f741-102">ISymUnmanagedDocument::GetLanguageVendor 方法</span><span class="sxs-lookup"><span data-stu-id="2f741-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="2f741-103">获取此文档的语言供应商。</span><span class="sxs-lookup"><span data-stu-id="2f741-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f741-104">语法</span><span class="sxs-lookup"><span data-stu-id="2f741-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f741-105">参数</span><span class="sxs-lookup"><span data-stu-id="2f741-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2f741-106">[out]指向接收的语言供应商的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="2f741-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f741-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2f741-107">Return Value</span></span>  
 <span data-ttu-id="2f741-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="2f741-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f741-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f741-109">See Also</span></span>  
 [<span data-ttu-id="2f741-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="2f741-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
