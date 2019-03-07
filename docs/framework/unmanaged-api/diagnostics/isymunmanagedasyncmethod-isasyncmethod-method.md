---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 方法
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 460d6781405b6042262d50e1aa79ee8c77f781a7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489717"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="c2f89-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 方法</span><span class="sxs-lookup"><span data-stu-id="c2f89-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="c2f89-103">检查该方法或不具有 async 信息。</span><span class="sxs-lookup"><span data-stu-id="c2f89-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="c2f89-104">如果此方法返回`FALSE`则是无效的调用此接口中的任何其他方法。</span><span class="sxs-lookup"><span data-stu-id="c2f89-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="c2f89-105">它们将所有返回`E_UNEXPECTED`这种情况下。</span><span class="sxs-lookup"><span data-stu-id="c2f89-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2f89-106">语法</span><span class="sxs-lookup"><span data-stu-id="c2f89-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2f89-107">参数</span><span class="sxs-lookup"><span data-stu-id="c2f89-107">Parameters</span></span>  
  
|<span data-ttu-id="c2f89-108">参数</span><span class="sxs-lookup"><span data-stu-id="c2f89-108">Parameter</span></span>|<span data-ttu-id="c2f89-109">描述</span><span class="sxs-lookup"><span data-stu-id="c2f89-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="c2f89-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c2f89-110">Return Value</span></span>  
 <span data-ttu-id="c2f89-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="c2f89-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2f89-112">要求</span><span class="sxs-lookup"><span data-stu-id="c2f89-112">Requirements</span></span>  
 <span data-ttu-id="c2f89-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c2f89-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f89-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2f89-114">See also</span></span>
- [<span data-ttu-id="c2f89-115">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="c2f89-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
