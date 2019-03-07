---
title: ISymENCUnmanagedMethod::GetDocumentsForMethodCount 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 571db05b5ec33a0bee310afadf205ac236f7048c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471532"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="91d6d-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount 方法</span><span class="sxs-lookup"><span data-stu-id="91d6d-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="91d6d-103">获取此方法中的行的文档数。</span><span class="sxs-lookup"><span data-stu-id="91d6d-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91d6d-104">语法</span><span class="sxs-lookup"><span data-stu-id="91d6d-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91d6d-105">参数</span><span class="sxs-lookup"><span data-stu-id="91d6d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="91d6d-106">[out]一个指向`ULONG32`接收包含文档所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="91d6d-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91d6d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="91d6d-107">Return Value</span></span>  
 <span data-ttu-id="91d6d-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="91d6d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91d6d-109">要求</span><span class="sxs-lookup"><span data-stu-id="91d6d-109">Requirements</span></span>  
 <span data-ttu-id="91d6d-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="91d6d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d6d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="91d6d-111">See also</span></span>
- [<span data-ttu-id="91d6d-112">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="91d6d-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
