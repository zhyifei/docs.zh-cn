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
ms.openlocfilehash: d7ba794060330de3934f8d4ca6434b09672d12bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090584"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="96e96-102">ISymUnmanagedVariable::GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="96e96-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="96e96-103">获取此变量的特性标志。</span><span class="sxs-lookup"><span data-stu-id="96e96-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e96-104">语法</span><span class="sxs-lookup"><span data-stu-id="96e96-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96e96-105">参数</span><span class="sxs-lookup"><span data-stu-id="96e96-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="96e96-106">[out]一个指向`ULONG32`接收属性。</span><span class="sxs-lookup"><span data-stu-id="96e96-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="96e96-107">返回的值将是中定义的值之一[CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="96e96-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96e96-108">返回值</span><span class="sxs-lookup"><span data-stu-id="96e96-108">Return Value</span></span>  
 <span data-ttu-id="96e96-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="96e96-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96e96-110">要求</span><span class="sxs-lookup"><span data-stu-id="96e96-110">Requirements</span></span>  
 <span data-ttu-id="96e96-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="96e96-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e96-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="96e96-112">See also</span></span>

- [<span data-ttu-id="96e96-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="96e96-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
