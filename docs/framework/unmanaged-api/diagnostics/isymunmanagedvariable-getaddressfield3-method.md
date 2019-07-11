---
title: ISymUnmanagedVariable::GetAddressField3 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76199dd18799c9f51f37d5b92e589effd7f45a57
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778297"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="adad0-102">ISymUnmanagedVariable::GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="adad0-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="adad0-103">获取此变量的第三个地址字段。</span><span class="sxs-lookup"><span data-stu-id="adad0-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="adad0-104">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="adad0-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adad0-105">语法</span><span class="sxs-lookup"><span data-stu-id="adad0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adad0-106">参数</span><span class="sxs-lookup"><span data-stu-id="adad0-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="adad0-107">[out]一个指向`ULONG32`，它接收的第三个地址字段。</span><span class="sxs-lookup"><span data-stu-id="adad0-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adad0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="adad0-108">Return Value</span></span>  
 <span data-ttu-id="adad0-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="adad0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adad0-110">要求</span><span class="sxs-lookup"><span data-stu-id="adad0-110">Requirements</span></span>  
 <span data-ttu-id="adad0-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="adad0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adad0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="adad0-112">See also</span></span>

- [<span data-ttu-id="adad0-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="adad0-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="adad0-114">GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="adad0-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="adad0-115">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="adad0-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="adad0-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="adad0-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
