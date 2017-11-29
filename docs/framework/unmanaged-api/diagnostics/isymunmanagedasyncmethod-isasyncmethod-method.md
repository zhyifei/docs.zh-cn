---
title: "ISymUnmanagedAsyncMethod::IsAsyncMethod 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ce91552d7468579d9941c1da75c4d281999d66fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="76e19-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 方法</span><span class="sxs-lookup"><span data-stu-id="76e19-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="76e19-103">检查是否，该方法是否具有异步信息。</span><span class="sxs-lookup"><span data-stu-id="76e19-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="76e19-104">如果此方法返回`FALSE`然后是无效调用此接口中的任何其他方法。</span><span class="sxs-lookup"><span data-stu-id="76e19-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="76e19-105">它们将所有返回`E_UNEXPECTED`在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="76e19-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e19-106">语法</span><span class="sxs-lookup"><span data-stu-id="76e19-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76e19-107">参数</span><span class="sxs-lookup"><span data-stu-id="76e19-107">Parameters</span></span>  
  
|<span data-ttu-id="76e19-108">参数</span><span class="sxs-lookup"><span data-stu-id="76e19-108">Parameter</span></span>|<span data-ttu-id="76e19-109">描述</span><span class="sxs-lookup"><span data-stu-id="76e19-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="76e19-110">返回值</span><span class="sxs-lookup"><span data-stu-id="76e19-110">Return Value</span></span>  
 <span data-ttu-id="76e19-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="76e19-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76e19-112">要求</span><span class="sxs-lookup"><span data-stu-id="76e19-112">Requirements</span></span>  
 <span data-ttu-id="76e19-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="76e19-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e19-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76e19-114">See Also</span></span>  
 [<span data-ttu-id="76e19-115">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="76e19-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
