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
ms.openlocfilehash: cea18fefa2d356cbb5857db5133b1086c38ac6ff
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449177"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="14991-102">ISymUnmanagedDocument::GetLanguage 方法</span><span class="sxs-lookup"><span data-stu-id="14991-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="14991-103">获取此文档的语言标识符</span><span class="sxs-lookup"><span data-stu-id="14991-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14991-104">语法</span><span class="sxs-lookup"><span data-stu-id="14991-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14991-105">参数</span><span class="sxs-lookup"><span data-stu-id="14991-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="14991-106">弄指向接收语言标识符的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="14991-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14991-107">返回值</span><span class="sxs-lookup"><span data-stu-id="14991-107">Return Value</span></span>  
 <span data-ttu-id="14991-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="14991-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14991-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14991-109">See also</span></span>

- [<span data-ttu-id="14991-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="14991-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
