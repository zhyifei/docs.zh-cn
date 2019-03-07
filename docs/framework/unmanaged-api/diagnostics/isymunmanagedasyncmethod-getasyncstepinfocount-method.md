---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 方法
ms.date: 03/30/2017
ms.assetid: 32a4e084-09b2-4946-a4a7-19a1fed9f7cc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31c8dbfc6562e2f5da42586160e2b23911fc2bfb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494631"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfocount-method"></a><span data-ttu-id="d84f3-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="d84f3-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount Method</span></span>
<span data-ttu-id="d84f3-103">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d84f3-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d84f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="d84f3-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfoCount(    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d84f3-105">参数</span><span class="sxs-lookup"><span data-stu-id="d84f3-105">Parameters</span></span>  
  
|<span data-ttu-id="d84f3-106">参数</span><span class="sxs-lookup"><span data-stu-id="d84f3-106">Parameter</span></span>|<span data-ttu-id="d84f3-107">描述</span><span class="sxs-lookup"><span data-stu-id="d84f3-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="d84f3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d84f3-108">Return Value</span></span>  
 <span data-ttu-id="d84f3-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="d84f3-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d84f3-110">要求</span><span class="sxs-lookup"><span data-stu-id="d84f3-110">Requirements</span></span>  
 <span data-ttu-id="d84f3-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d84f3-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d84f3-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d84f3-112">See also</span></span>
- [<span data-ttu-id="d84f3-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="d84f3-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
