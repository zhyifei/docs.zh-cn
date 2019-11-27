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
ms.openlocfilehash: cfc28dfcda7bf4b3d1fc6fe3530a212ee76fadd2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446087"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="0cb28-102">ISymUnmanagedVariable::GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="0cb28-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="0cb28-103">获取此变量的特性标志。</span><span class="sxs-lookup"><span data-stu-id="0cb28-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cb28-104">语法</span><span class="sxs-lookup"><span data-stu-id="0cb28-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cb28-105">参数</span><span class="sxs-lookup"><span data-stu-id="0cb28-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0cb28-106">弄指向接收特性的 `ULONG32` 的指针。</span><span class="sxs-lookup"><span data-stu-id="0cb28-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="0cb28-107">返回的值将是[CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md)枚举中定义的值之一。</span><span class="sxs-lookup"><span data-stu-id="0cb28-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cb28-108">返回值</span><span class="sxs-lookup"><span data-stu-id="0cb28-108">Return Value</span></span>  
 <span data-ttu-id="0cb28-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="0cb28-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cb28-110">要求</span><span class="sxs-lookup"><span data-stu-id="0cb28-110">Requirements</span></span>  
 <span data-ttu-id="0cb28-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="0cb28-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb28-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cb28-112">See also</span></span>

- [<span data-ttu-id="0cb28-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="0cb28-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
