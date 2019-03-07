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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11ab9f8077a4b2a9e97c321c6edbe629dc0de19d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500728"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="d217c-102">ISymUnmanagedDocument::GetSourceLength 方法</span><span class="sxs-lookup"><span data-stu-id="d217c-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="d217c-103">获取嵌入源的长度（以字节表示）。</span><span class="sxs-lookup"><span data-stu-id="d217c-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d217c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d217c-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d217c-105">参数</span><span class="sxs-lookup"><span data-stu-id="d217c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d217c-106">[out]指向指示嵌入源的长度，以字节为单位的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="d217c-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d217c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d217c-107">Return Value</span></span>  
 <span data-ttu-id="d217c-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d217c-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d217c-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="d217c-109">See also</span></span>
- [<span data-ttu-id="d217c-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="d217c-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
