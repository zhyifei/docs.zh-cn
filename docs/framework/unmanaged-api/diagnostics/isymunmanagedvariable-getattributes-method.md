---
title: ISymUnmanagedVariable::GetAttributes 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d418a1088f9ee23a088ab4c8246810d2c9bee4fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574334"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="6ec1c-102">ISymUnmanagedVariable::GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="6ec1c-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="6ec1c-103">获取此变量的特性标志。</span><span class="sxs-lookup"><span data-stu-id="6ec1c-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ec1c-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ec1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ec1c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6ec1c-106">[out]一个指向`ULONG32`接收属性。</span><span class="sxs-lookup"><span data-stu-id="6ec1c-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="6ec1c-107">返回的值将是中定义的值之一[CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="6ec1c-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ec1c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="6ec1c-108">Return Value</span></span>  
 <span data-ttu-id="6ec1c-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="6ec1c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ec1c-110">要求</span><span class="sxs-lookup"><span data-stu-id="6ec1c-110">Requirements</span></span>  
 <span data-ttu-id="6ec1c-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6ec1c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec1c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ec1c-112">See also</span></span>
- [<span data-ttu-id="6ec1c-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="6ec1c-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
