---
title: ISymUnmanagedVariable::GetAddressField1 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
ms.openlocfilehash: a59b50009e7f0ab2fff1b8439e368234403822c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446129"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="4a2da-102">ISymUnmanagedVariable::GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="4a2da-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="4a2da-103">Gets the first address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="4a2da-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="4a2da-104">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="4a2da-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a2da-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a2da-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a2da-106">参数</span><span class="sxs-lookup"><span data-stu-id="4a2da-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4a2da-107">[out] A pointer to a `ULONG32` that receives the first address field.</span><span class="sxs-lookup"><span data-stu-id="4a2da-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a2da-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4a2da-108">Return Value</span></span>  
 <span data-ttu-id="4a2da-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="4a2da-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a2da-110">要求</span><span class="sxs-lookup"><span data-stu-id="4a2da-110">Requirements</span></span>  
 <span data-ttu-id="4a2da-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4a2da-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a2da-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a2da-112">See also</span></span>

- [<span data-ttu-id="4a2da-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="4a2da-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="4a2da-114">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="4a2da-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="4a2da-115">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="4a2da-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="4a2da-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="4a2da-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
