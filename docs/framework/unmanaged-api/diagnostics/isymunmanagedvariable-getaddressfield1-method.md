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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 796a71ac941497801c749295fb2f6bb201547bd7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478305"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="35f71-102">ISymUnmanagedVariable::GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="35f71-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="35f71-103">获取此变量的第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="35f71-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="35f71-104">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="35f71-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35f71-105">语法</span><span class="sxs-lookup"><span data-stu-id="35f71-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35f71-106">参数</span><span class="sxs-lookup"><span data-stu-id="35f71-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="35f71-107">[out]一个指向`ULONG32`，它接收的第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="35f71-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35f71-108">返回值</span><span class="sxs-lookup"><span data-stu-id="35f71-108">Return Value</span></span>  
 <span data-ttu-id="35f71-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="35f71-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35f71-110">要求</span><span class="sxs-lookup"><span data-stu-id="35f71-110">Requirements</span></span>  
 <span data-ttu-id="35f71-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="35f71-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f71-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="35f71-112">See also</span></span>
- [<span data-ttu-id="35f71-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="35f71-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="35f71-114">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="35f71-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="35f71-115">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="35f71-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="35f71-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="35f71-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
