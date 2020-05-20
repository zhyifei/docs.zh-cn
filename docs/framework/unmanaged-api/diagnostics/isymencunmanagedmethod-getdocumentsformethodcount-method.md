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
ms.openlocfilehash: d096101189d52401c407a4108c9c81e201d3f30d
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441937"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="c65a2-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount 方法</span><span class="sxs-lookup"><span data-stu-id="c65a2-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="c65a2-103">获取此方法在中包含行的文档数。</span><span class="sxs-lookup"><span data-stu-id="c65a2-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c65a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="c65a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c65a2-105">参数</span><span class="sxs-lookup"><span data-stu-id="c65a2-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c65a2-106">弄指向的指针 `ULONG32` ，该指针接收包含文档所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="c65a2-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c65a2-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c65a2-107">Return Value</span></span>  
 <span data-ttu-id="c65a2-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="c65a2-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c65a2-109">要求</span><span class="sxs-lookup"><span data-stu-id="c65a2-109">Requirements</span></span>  
 <span data-ttu-id="c65a2-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="c65a2-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65a2-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c65a2-111">See also</span></span>

- [<span data-ttu-id="c65a2-112">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="c65a2-112">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
