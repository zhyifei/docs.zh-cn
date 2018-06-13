---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 方法
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f5bf8252986ffa90ea5380d5342595cb91e5419
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424936"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="37353-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 方法</span><span class="sxs-lookup"><span data-stu-id="37353-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="37353-103">检查是否，该方法是否具有异步信息。</span><span class="sxs-lookup"><span data-stu-id="37353-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="37353-104">如果此方法返回`FALSE`然后是无效调用此接口中的任何其他方法。</span><span class="sxs-lookup"><span data-stu-id="37353-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="37353-105">它们将所有返回`E_UNEXPECTED`在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="37353-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37353-106">语法</span><span class="sxs-lookup"><span data-stu-id="37353-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37353-107">参数</span><span class="sxs-lookup"><span data-stu-id="37353-107">Parameters</span></span>  
  
|<span data-ttu-id="37353-108">参数</span><span class="sxs-lookup"><span data-stu-id="37353-108">Parameter</span></span>|<span data-ttu-id="37353-109">描述</span><span class="sxs-lookup"><span data-stu-id="37353-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="37353-110">返回值</span><span class="sxs-lookup"><span data-stu-id="37353-110">Return Value</span></span>  
 <span data-ttu-id="37353-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="37353-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37353-112">要求</span><span class="sxs-lookup"><span data-stu-id="37353-112">Requirements</span></span>  
 <span data-ttu-id="37353-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="37353-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37353-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="37353-114">See Also</span></span>  
 [<span data-ttu-id="37353-115">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="37353-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
