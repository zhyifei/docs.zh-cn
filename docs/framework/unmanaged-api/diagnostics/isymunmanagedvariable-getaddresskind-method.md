---
title: ISymUnmanagedVariable::GetAddressKind 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8b45cda05a386efef320d2caad0ed241a4767b9c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484844"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="bad1c-102">ISymUnmanagedVariable::GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="bad1c-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="bad1c-103">获取此变量的地址类型。</span><span class="sxs-lookup"><span data-stu-id="bad1c-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="bad1c-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bad1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="bad1c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bad1c-106">[out]一个指向`ULONG32`接收的值。</span><span class="sxs-lookup"><span data-stu-id="bad1c-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="bad1c-107">可能的值中定义[CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="bad1c-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bad1c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="bad1c-108">Return Value</span></span>  
 <span data-ttu-id="bad1c-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="bad1c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bad1c-110">要求</span><span class="sxs-lookup"><span data-stu-id="bad1c-110">Requirements</span></span>  
 <span data-ttu-id="bad1c-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bad1c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad1c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="bad1c-112">See also</span></span>
- [<span data-ttu-id="bad1c-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="bad1c-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
