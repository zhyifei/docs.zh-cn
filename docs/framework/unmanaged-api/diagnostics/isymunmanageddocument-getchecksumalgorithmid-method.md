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
ms.openlocfilehash: a76435be591d9f73d5975c5315f6e744f8972fc7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614612"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="b3599-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId 方法</span><span class="sxs-lookup"><span data-stu-id="b3599-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="b3599-103">如果没有校验和，则获取校验和算法标识符，或返回所有零的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b3599-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3599-104">语法</span><span class="sxs-lookup"><span data-stu-id="b3599-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3599-105">参数</span><span class="sxs-lookup"><span data-stu-id="b3599-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b3599-106">弄指向接收校验和算法标识符的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="b3599-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3599-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b3599-107">Return Value</span></span>  
 <span data-ttu-id="b3599-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b3599-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3599-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3599-109">See also</span></span>

- [<span data-ttu-id="b3599-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="b3599-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
