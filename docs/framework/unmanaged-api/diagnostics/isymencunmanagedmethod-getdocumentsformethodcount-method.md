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
ms.openlocfilehash: f3c7f7e06822f419282209ac39d4cbd46e600a66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424984"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="df99f-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount 方法</span><span class="sxs-lookup"><span data-stu-id="df99f-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="df99f-103">获取此方法的行中的文档数。</span><span class="sxs-lookup"><span data-stu-id="df99f-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df99f-104">语法</span><span class="sxs-lookup"><span data-stu-id="df99f-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df99f-105">参数</span><span class="sxs-lookup"><span data-stu-id="df99f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="df99f-106">[out]指向的指针`ULONG32`接收包含文档所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="df99f-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df99f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="df99f-107">Return Value</span></span>  
 <span data-ttu-id="df99f-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="df99f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df99f-109">要求</span><span class="sxs-lookup"><span data-stu-id="df99f-109">Requirements</span></span>  
 <span data-ttu-id="df99f-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df99f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df99f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="df99f-111">See Also</span></span>  
 [<span data-ttu-id="df99f-112">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="df99f-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
