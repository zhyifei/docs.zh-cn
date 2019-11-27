---
title: ISymUnmanagedDocument::GetCheckSumAlgorithmId 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 2bc673d2e331cd32d5317cb20f9418eb3a3b144a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431064"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="1d5e0-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId 方法</span><span class="sxs-lookup"><span data-stu-id="1d5e0-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="1d5e0-103">如果没有校验和，则获取校验和算法标识符，或返回所有零的 GUID。</span><span class="sxs-lookup"><span data-stu-id="1d5e0-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d5e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d5e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d5e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d5e0-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1d5e0-106">弄指向接收校验和算法标识符的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="1d5e0-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d5e0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1d5e0-107">Return Value</span></span>  
 <span data-ttu-id="1d5e0-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="1d5e0-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d5e0-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d5e0-109">See also</span></span>

- [<span data-ttu-id="1d5e0-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="1d5e0-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
