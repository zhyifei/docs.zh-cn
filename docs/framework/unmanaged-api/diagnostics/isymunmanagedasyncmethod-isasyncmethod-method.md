---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 方法
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 91b4c2688dadf12fa4a835a662622267d7831cf8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441794"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="c9a33-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 方法</span><span class="sxs-lookup"><span data-stu-id="c9a33-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="c9a33-103">检查方法是否有异步信息。</span><span class="sxs-lookup"><span data-stu-id="c9a33-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="c9a33-104">如果此方法返回，则 `FALSE` 调用此接口中的任何其他方法无效。</span><span class="sxs-lookup"><span data-stu-id="c9a33-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="c9a33-105">`E_UNEXPECTED`在这种情况下，它们都将返回。</span><span class="sxs-lookup"><span data-stu-id="c9a33-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a33-106">语法</span><span class="sxs-lookup"><span data-stu-id="c9a33-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9a33-107">参数</span><span class="sxs-lookup"><span data-stu-id="c9a33-107">Parameters</span></span>  
  
|<span data-ttu-id="c9a33-108">参数</span><span class="sxs-lookup"><span data-stu-id="c9a33-108">Parameter</span></span>|<span data-ttu-id="c9a33-109">说明</span><span class="sxs-lookup"><span data-stu-id="c9a33-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="c9a33-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c9a33-110">Return Value</span></span>  
 <span data-ttu-id="c9a33-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="c9a33-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9a33-112">要求</span><span class="sxs-lookup"><span data-stu-id="c9a33-112">Requirements</span></span>  
 <span data-ttu-id="c9a33-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="c9a33-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a33-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9a33-114">See also</span></span>

- [<span data-ttu-id="c9a33-115">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="c9a33-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
