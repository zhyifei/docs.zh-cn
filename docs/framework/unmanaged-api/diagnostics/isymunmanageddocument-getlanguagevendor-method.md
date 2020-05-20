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
ms.openlocfilehash: e0a4c190f0f8e91886563477500c0e57e3516dfa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614560"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="c84cc-102">ISymUnmanagedDocument::GetLanguageVendor 方法</span><span class="sxs-lookup"><span data-stu-id="c84cc-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="c84cc-103">获取此文档的语言供应商。</span><span class="sxs-lookup"><span data-stu-id="c84cc-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c84cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="c84cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c84cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="c84cc-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c84cc-106">弄指向接收语言供应商的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="c84cc-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c84cc-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c84cc-107">Return Value</span></span>  
 <span data-ttu-id="c84cc-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="c84cc-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c84cc-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c84cc-109">See also</span></span>

- [<span data-ttu-id="c84cc-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="c84cc-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
