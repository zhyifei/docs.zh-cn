---
title: ISymUnmanagedConstant::GetValue 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f51a41e8f00a0cf88b11078468ba5a8511fd1391
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424734"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="2d7e1-102">ISymUnmanagedConstant::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="2d7e1-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="2d7e1-103">获取该常量的值。</span><span class="sxs-lookup"><span data-stu-id="2d7e1-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d7e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d7e1-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d7e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d7e1-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="2d7e1-106">[out]指向接收的值的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="2d7e1-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d7e1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2d7e1-107">Return Value</span></span>  
 <span data-ttu-id="2d7e1-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="2d7e1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d7e1-109">要求</span><span class="sxs-lookup"><span data-stu-id="2d7e1-109">Requirements</span></span>  
 <span data-ttu-id="2d7e1-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d7e1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d7e1-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d7e1-111">See Also</span></span>  
 [<span data-ttu-id="2d7e1-112">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="2d7e1-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="2d7e1-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="2d7e1-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="2d7e1-114">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="2d7e1-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
