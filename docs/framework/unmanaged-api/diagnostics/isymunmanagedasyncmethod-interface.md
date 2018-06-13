---
title: ISymUnmanagedAsyncMethod 接口
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cefad27d8b9314b45dec6100e35a54990fb591c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427994"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="d5256-102">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="d5256-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="d5256-103">此接口是对读取补充[ISymUnmanagedAsyncMethodPropertiesWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="d5256-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5256-104">语法</span><span class="sxs-lookup"><span data-stu-id="d5256-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="d5256-105">方法</span><span class="sxs-lookup"><span data-stu-id="d5256-105">Methods</span></span>  
 <span data-ttu-id="d5256-106">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="d5256-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="d5256-107">方法</span><span class="sxs-lookup"><span data-stu-id="d5256-107">Method</span></span>|<span data-ttu-id="d5256-108">描述</span><span class="sxs-lookup"><span data-stu-id="d5256-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5256-109">GetAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="d5256-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="d5256-110">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d5256-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="d5256-111">GetAsyncStepInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="d5256-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="d5256-112">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d5256-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="d5256-113">GetCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="d5256-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="d5256-114">请参阅[DefineCatchHandlerILOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d5256-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="d5256-115">GetKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="d5256-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="d5256-116">请参阅[DefineKickoffMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d5256-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="d5256-117">HasCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="d5256-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="d5256-118">请参阅[DefineCatchHandlerILOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d5256-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="d5256-119">IsAsyncMethod 方法</span><span class="sxs-lookup"><span data-stu-id="d5256-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="d5256-120">检查是否，该方法是否具有异步信息。</span><span class="sxs-lookup"><span data-stu-id="d5256-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="d5256-121">如果此方法返回`FALSE`然后是无效调用此接口中的任何其他方法。</span><span class="sxs-lookup"><span data-stu-id="d5256-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="d5256-122">它们将所有返回`E_UNEXPECTED`在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="d5256-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5256-123">要求</span><span class="sxs-lookup"><span data-stu-id="d5256-123">Requirements</span></span>  
 <span data-ttu-id="d5256-124">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d5256-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5256-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5256-125">See Also</span></span>  
 [<span data-ttu-id="d5256-126">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="d5256-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
