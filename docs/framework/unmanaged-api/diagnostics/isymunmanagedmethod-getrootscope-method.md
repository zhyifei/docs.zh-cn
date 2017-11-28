---
title: "ISymUnmanagedMethod::GetRootScope 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetRootScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82b03e6db75d69d1d36f0137922448bad165e6ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="f7386-102">ISymUnmanagedMethod::GetRootScope 方法</span><span class="sxs-lookup"><span data-stu-id="f7386-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="f7386-103">获取在此方法内的根词法范围。</span><span class="sxs-lookup"><span data-stu-id="f7386-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="f7386-104">此范围包括整个方法。</span><span class="sxs-lookup"><span data-stu-id="f7386-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7386-105">语法</span><span class="sxs-lookup"><span data-stu-id="f7386-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7386-106">参数</span><span class="sxs-lookup"><span data-stu-id="f7386-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f7386-107">[out]一个指针，它设置为返回[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f7386-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7386-108">返回值</span><span class="sxs-lookup"><span data-stu-id="f7386-108">Return Value</span></span>  
 <span data-ttu-id="f7386-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="f7386-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7386-110">要求</span><span class="sxs-lookup"><span data-stu-id="f7386-110">Requirements</span></span>  
 <span data-ttu-id="f7386-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f7386-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7386-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7386-112">See Also</span></span>  
 [<span data-ttu-id="f7386-113">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="f7386-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
