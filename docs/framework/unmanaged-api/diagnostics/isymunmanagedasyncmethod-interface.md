---
title: ISymUnmanagedAsyncMethod 接口
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 0b8adba9dbffbdc47bb526cef9aad3ffa4b48065
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129229"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="e8e29-102">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="e8e29-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="e8e29-103">此接口是[ISymUnmanagedAsyncMethodPropertiesWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)的读取补充。</span><span class="sxs-lookup"><span data-stu-id="e8e29-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e29-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8e29-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="e8e29-105">方法</span><span class="sxs-lookup"><span data-stu-id="e8e29-105">Methods</span></span>  
 <span data-ttu-id="e8e29-106">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="e8e29-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="e8e29-107">方法</span><span class="sxs-lookup"><span data-stu-id="e8e29-107">Method</span></span>|<span data-ttu-id="e8e29-108">描述</span><span class="sxs-lookup"><span data-stu-id="e8e29-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8e29-109">GetAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="e8e29-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="e8e29-110">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e29-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="e8e29-111">GetAsyncStepInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="e8e29-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="e8e29-112">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e29-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="e8e29-113">GetCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="e8e29-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="e8e29-114">请参阅[DefineCatchHandlerILOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e29-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="e8e29-115">GetKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="e8e29-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="e8e29-116">请参阅[DefineKickoffMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e29-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="e8e29-117">HasCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="e8e29-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="e8e29-118">请参阅[DefineCatchHandlerILOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e29-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="e8e29-119">IsAsyncMethod 方法</span><span class="sxs-lookup"><span data-stu-id="e8e29-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="e8e29-120">检查方法是否有异步信息。</span><span class="sxs-lookup"><span data-stu-id="e8e29-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="e8e29-121">如果此方法返回 `FALSE` 则调用此接口中的任何其他方法无效。</span><span class="sxs-lookup"><span data-stu-id="e8e29-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="e8e29-122">在这种情况下，它们都将返回 `E_UNEXPECTED`。</span><span class="sxs-lookup"><span data-stu-id="e8e29-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8e29-123">要求</span><span class="sxs-lookup"><span data-stu-id="e8e29-123">Requirements</span></span>  
 <span data-ttu-id="e8e29-124">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e8e29-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e29-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8e29-125">See also</span></span>

- [<span data-ttu-id="e8e29-126">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="e8e29-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
