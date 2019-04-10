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
ms.openlocfilehash: 9eac17ec9599caba88ddaa73d28abcae538a4d19
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215061"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="62023-102">ISymUnmanagedMethod::GetSequencePointCount 方法</span><span class="sxs-lookup"><span data-stu-id="62023-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="62023-103">获取在此方法内的序列点的计数。</span><span class="sxs-lookup"><span data-stu-id="62023-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62023-104">语法</span><span class="sxs-lookup"><span data-stu-id="62023-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62023-105">参数</span><span class="sxs-lookup"><span data-stu-id="62023-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="62023-106">[out]一个指向`ULONG32`接收包含序列点所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="62023-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62023-107">返回值</span><span class="sxs-lookup"><span data-stu-id="62023-107">Return Value</span></span>  
 <span data-ttu-id="62023-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="62023-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62023-109">要求</span><span class="sxs-lookup"><span data-stu-id="62023-109">Requirements</span></span>  
 <span data-ttu-id="62023-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="62023-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62023-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="62023-111">See also</span></span>

- [<span data-ttu-id="62023-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="62023-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
