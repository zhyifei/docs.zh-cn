---
title: "ISymUnmanagedConstant::GetValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 15ae3e9f2e680c7e85d3b8daa0d6010773797258
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="25249-102">ISymUnmanagedConstant::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="25249-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="25249-103">获取该常量的值。</span><span class="sxs-lookup"><span data-stu-id="25249-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25249-104">语法</span><span class="sxs-lookup"><span data-stu-id="25249-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25249-105">参数</span><span class="sxs-lookup"><span data-stu-id="25249-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="25249-106">[out]指向接收的值的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="25249-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25249-107">返回值</span><span class="sxs-lookup"><span data-stu-id="25249-107">Return Value</span></span>  
 <span data-ttu-id="25249-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="25249-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25249-109">惠?</span><span class="sxs-lookup"><span data-stu-id="25249-109">Requirements</span></span>  
 <span data-ttu-id="25249-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="25249-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25249-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="25249-111">See Also</span></span>  
 [<span data-ttu-id="25249-112">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="25249-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="25249-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="25249-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="25249-114">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="25249-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
