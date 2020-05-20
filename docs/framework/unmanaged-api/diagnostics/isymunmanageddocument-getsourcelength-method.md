---
title: ISymUnmanagedDocument::GetSourceLength 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
ms.openlocfilehash: e84639c1d63e6935b9b363f01c12bf0fbd3390e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615613"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="e7b31-102">ISymUnmanagedDocument::GetSourceLength 方法</span><span class="sxs-lookup"><span data-stu-id="e7b31-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="e7b31-103">获取嵌入源的长度（以字节表示）。</span><span class="sxs-lookup"><span data-stu-id="e7b31-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7b31-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7b31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7b31-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7b31-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e7b31-106">弄指向变量的指针，该变量指示嵌入源的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e7b31-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7b31-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e7b31-107">Return Value</span></span>  
 <span data-ttu-id="e7b31-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="e7b31-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b31-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7b31-109">See also</span></span>

- [<span data-ttu-id="e7b31-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="e7b31-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
