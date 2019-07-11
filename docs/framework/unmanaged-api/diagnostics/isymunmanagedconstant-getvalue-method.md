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
ms.openlocfilehash: e89dabeeb4956d106e8d0ca83520d87f3b330e63
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776812"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="53f30-102">ISymUnmanagedConstant::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="53f30-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="53f30-103">获取常量的值。</span><span class="sxs-lookup"><span data-stu-id="53f30-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f30-104">语法</span><span class="sxs-lookup"><span data-stu-id="53f30-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53f30-105">参数</span><span class="sxs-lookup"><span data-stu-id="53f30-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="53f30-106">[out]指向一个变量来接收值的指针。</span><span class="sxs-lookup"><span data-stu-id="53f30-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53f30-107">返回值</span><span class="sxs-lookup"><span data-stu-id="53f30-107">Return Value</span></span>  
 <span data-ttu-id="53f30-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="53f30-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53f30-109">要求</span><span class="sxs-lookup"><span data-stu-id="53f30-109">Requirements</span></span>  
 <span data-ttu-id="53f30-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="53f30-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f30-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="53f30-111">See also</span></span>

- [<span data-ttu-id="53f30-112">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="53f30-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="53f30-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="53f30-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="53f30-114">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="53f30-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
