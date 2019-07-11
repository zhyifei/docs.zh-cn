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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b631b16334b7e5019376fbb9a3f65d7fc2ced7dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776754"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="3ddc0-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId 方法</span><span class="sxs-lookup"><span data-stu-id="3ddc0-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="3ddc0-103">获取校验和算法标识符，或如果没有校验和，则返回全部为零的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3ddc0-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ddc0-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ddc0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ddc0-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ddc0-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3ddc0-106">[out]指向一个变量来接收校验和算法标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="3ddc0-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ddc0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3ddc0-107">Return Value</span></span>  
 <span data-ttu-id="3ddc0-108">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="3ddc0-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ddc0-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ddc0-109">See also</span></span>

- [<span data-ttu-id="3ddc0-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="3ddc0-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
