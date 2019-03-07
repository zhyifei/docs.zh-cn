---
title: ISymUnmanagedScope2::GetConstantCount 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d1dfc9ead6256ae700d5e619da4fae5745bdd759
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485145"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="dae3e-102">ISymUnmanagedScope2::GetConstantCount 方法</span><span class="sxs-lookup"><span data-stu-id="dae3e-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="dae3e-103">获取此范围内定义的常量的计数。</span><span class="sxs-lookup"><span data-stu-id="dae3e-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dae3e-104">语法</span><span class="sxs-lookup"><span data-stu-id="dae3e-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dae3e-105">参数</span><span class="sxs-lookup"><span data-stu-id="dae3e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="dae3e-106">[out]一个指向`ULONG32`用于接收大小，以字符为单位，以包含常量的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="dae3e-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dae3e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="dae3e-107">Return Value</span></span>  
 <span data-ttu-id="dae3e-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="dae3e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dae3e-109">要求</span><span class="sxs-lookup"><span data-stu-id="dae3e-109">Requirements</span></span>  
 <span data-ttu-id="dae3e-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dae3e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae3e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="dae3e-111">See also</span></span>
- [<span data-ttu-id="dae3e-112">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="dae3e-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
