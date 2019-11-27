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
ms.openlocfilehash: 00be35e9a15349b8bca5f76b948b8477dd240888
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449236"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="97808-102">ISymUnmanagedConstant::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="97808-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="97808-103">获取常量的值。</span><span class="sxs-lookup"><span data-stu-id="97808-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97808-104">语法</span><span class="sxs-lookup"><span data-stu-id="97808-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97808-105">参数</span><span class="sxs-lookup"><span data-stu-id="97808-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="97808-106">弄指向接收值的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="97808-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97808-107">返回值</span><span class="sxs-lookup"><span data-stu-id="97808-107">Return Value</span></span>  
 <span data-ttu-id="97808-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="97808-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97808-109">要求</span><span class="sxs-lookup"><span data-stu-id="97808-109">Requirements</span></span>  
 <span data-ttu-id="97808-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="97808-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97808-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97808-111">See also</span></span>

- [<span data-ttu-id="97808-112">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="97808-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="97808-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="97808-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="97808-114">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="97808-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
