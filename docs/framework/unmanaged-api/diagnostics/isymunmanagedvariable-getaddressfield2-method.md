---
title: ISymUnmanagedVariable::GetAddressField2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a283915f8326a19c7d2c9b45851b9879fe0ec17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634982"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="b29d5-102">ISymUnmanagedVariable::GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="b29d5-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="b29d5-103">获取此变量的第二个地址字段。</span><span class="sxs-lookup"><span data-stu-id="b29d5-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="b29d5-104">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="b29d5-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b29d5-105">语法</span><span class="sxs-lookup"><span data-stu-id="b29d5-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b29d5-106">参数</span><span class="sxs-lookup"><span data-stu-id="b29d5-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b29d5-107">[out]一个指向`ULONG32`接收第二个地址字段。</span><span class="sxs-lookup"><span data-stu-id="b29d5-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b29d5-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b29d5-108">Return Value</span></span>  
 <span data-ttu-id="b29d5-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="b29d5-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b29d5-110">要求</span><span class="sxs-lookup"><span data-stu-id="b29d5-110">Requirements</span></span>  
 <span data-ttu-id="b29d5-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b29d5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29d5-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b29d5-112">See also</span></span>
- [<span data-ttu-id="b29d5-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="b29d5-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="b29d5-114">GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="b29d5-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="b29d5-115">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="b29d5-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="b29d5-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="b29d5-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
