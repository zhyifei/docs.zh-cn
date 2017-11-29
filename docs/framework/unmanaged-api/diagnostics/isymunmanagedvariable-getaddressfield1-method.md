---
title: "ISymUnmanagedVariable::GetAddressField1 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAddressField1
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 460535813ed684424ae51710f09c731505805773
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="93428-102">ISymUnmanagedVariable::GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="93428-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="93428-103">获取此变量的第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="93428-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="93428-104">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="93428-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93428-105">语法</span><span class="sxs-lookup"><span data-stu-id="93428-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93428-106">参数</span><span class="sxs-lookup"><span data-stu-id="93428-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="93428-107">[out]指向的指针`ULONG32`接收第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="93428-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93428-108">返回值</span><span class="sxs-lookup"><span data-stu-id="93428-108">Return Value</span></span>  
 <span data-ttu-id="93428-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="93428-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93428-110">要求</span><span class="sxs-lookup"><span data-stu-id="93428-110">Requirements</span></span>  
 <span data-ttu-id="93428-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="93428-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93428-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93428-112">See Also</span></span>  
 [<span data-ttu-id="93428-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="93428-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="93428-114">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="93428-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="93428-115">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="93428-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)  
 [<span data-ttu-id="93428-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="93428-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
