---
title: ISymUnmanagedMethod::GetSequencePointCount 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1a9ef59cfe63ba745e6f5eba3ba2c3f3f983886
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="e264d-102">ISymUnmanagedMethod::GetSequencePointCount 方法</span><span class="sxs-lookup"><span data-stu-id="e264d-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="e264d-103">获取在此方法内的序列点的计数。</span><span class="sxs-lookup"><span data-stu-id="e264d-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e264d-104">语法</span><span class="sxs-lookup"><span data-stu-id="e264d-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e264d-105">参数</span><span class="sxs-lookup"><span data-stu-id="e264d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e264d-106">[out]指向的指针`ULONG32`接收包含序列点所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="e264d-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e264d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e264d-107">Return Value</span></span>  
 <span data-ttu-id="e264d-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e264d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e264d-109">要求</span><span class="sxs-lookup"><span data-stu-id="e264d-109">Requirements</span></span>  
 <span data-ttu-id="e264d-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e264d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e264d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e264d-111">See Also</span></span>  
 [<span data-ttu-id="e264d-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="e264d-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
