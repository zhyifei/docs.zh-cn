---
title: "ISymUnmanagedVariable::GetAttributes 方法"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fa57fcb214f465a57af9638d6f5a44acf746225
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="4890e-102">ISymUnmanagedVariable::GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="4890e-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="4890e-103">获取此变量的属性的标志。</span><span class="sxs-lookup"><span data-stu-id="4890e-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4890e-104">语法</span><span class="sxs-lookup"><span data-stu-id="4890e-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4890e-105">参数</span><span class="sxs-lookup"><span data-stu-id="4890e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4890e-106">[out]指向的指针`ULONG32`接收属性。</span><span class="sxs-lookup"><span data-stu-id="4890e-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="4890e-107">返回的值将为中定义的值之一[CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="4890e-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4890e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4890e-108">Return Value</span></span>  
 <span data-ttu-id="4890e-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="4890e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4890e-110">惠?</span><span class="sxs-lookup"><span data-stu-id="4890e-110">Requirements</span></span>  
 <span data-ttu-id="4890e-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4890e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4890e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4890e-112">See Also</span></span>  
 [<span data-ttu-id="4890e-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="4890e-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
