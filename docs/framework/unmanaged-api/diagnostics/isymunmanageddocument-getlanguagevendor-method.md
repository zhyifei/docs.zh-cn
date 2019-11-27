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
ms.openlocfilehash: cea2c161211dd74a46818c9b3c641852ea9999cd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449170"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="2a431-102">ISymUnmanagedDocument::GetLanguageVendor 方法</span><span class="sxs-lookup"><span data-stu-id="2a431-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="2a431-103">获取此文档的语言供应商。</span><span class="sxs-lookup"><span data-stu-id="2a431-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a431-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a431-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a431-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a431-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2a431-106">弄指向接收语言供应商的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="2a431-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a431-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2a431-107">Return Value</span></span>  
 <span data-ttu-id="2a431-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="2a431-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a431-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a431-109">See also</span></span>

- [<span data-ttu-id="2a431-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="2a431-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
