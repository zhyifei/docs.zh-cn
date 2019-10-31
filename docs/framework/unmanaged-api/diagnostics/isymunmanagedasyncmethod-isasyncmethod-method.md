---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 方法
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 0ea4c21e9e6a49d7bbbad5e1853598c440cd6410
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129213"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="142fc-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 方法</span><span class="sxs-lookup"><span data-stu-id="142fc-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="142fc-103">检查方法是否有异步信息。</span><span class="sxs-lookup"><span data-stu-id="142fc-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="142fc-104">如果此方法返回 `FALSE` 则调用此接口中的任何其他方法无效。</span><span class="sxs-lookup"><span data-stu-id="142fc-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="142fc-105">在这种情况下，它们都将返回 `E_UNEXPECTED`。</span><span class="sxs-lookup"><span data-stu-id="142fc-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="142fc-106">语法</span><span class="sxs-lookup"><span data-stu-id="142fc-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="142fc-107">参数</span><span class="sxs-lookup"><span data-stu-id="142fc-107">Parameters</span></span>  
  
|<span data-ttu-id="142fc-108">参数</span><span class="sxs-lookup"><span data-stu-id="142fc-108">Parameter</span></span>|<span data-ttu-id="142fc-109">描述</span><span class="sxs-lookup"><span data-stu-id="142fc-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="142fc-110">返回值</span><span class="sxs-lookup"><span data-stu-id="142fc-110">Return Value</span></span>  
 <span data-ttu-id="142fc-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="142fc-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="142fc-112">要求</span><span class="sxs-lookup"><span data-stu-id="142fc-112">Requirements</span></span>  
 <span data-ttu-id="142fc-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="142fc-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142fc-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="142fc-114">See also</span></span>

- [<span data-ttu-id="142fc-115">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="142fc-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
