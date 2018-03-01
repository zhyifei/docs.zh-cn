---
title: "ISymUnmanagedDocument::GetCheckSumAlgorithmId 方法"
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
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 58fbb5ae13433e0faa47db1e1e49d086670e69d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="75f2f-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId 方法</span><span class="sxs-lookup"><span data-stu-id="75f2f-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="75f2f-103">获取校验和算法标识符，或如果没有校验和，则返回全为零的 GUID。</span><span class="sxs-lookup"><span data-stu-id="75f2f-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f2f-104">语法</span><span class="sxs-lookup"><span data-stu-id="75f2f-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75f2f-105">参数</span><span class="sxs-lookup"><span data-stu-id="75f2f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="75f2f-106">[out]指向接收校验和算法标识符的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="75f2f-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75f2f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="75f2f-107">Return Value</span></span>  
 <span data-ttu-id="75f2f-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="75f2f-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f2f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="75f2f-109">See Also</span></span>  
 [<span data-ttu-id="75f2f-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="75f2f-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
