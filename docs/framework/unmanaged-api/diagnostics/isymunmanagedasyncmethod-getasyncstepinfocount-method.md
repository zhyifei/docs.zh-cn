---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 方法
ms.date: 03/30/2017
ms.assetid: 32a4e084-09b2-4946-a4a7-19a1fed9f7cc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1a839291c14b093aceb220810764c40f5b468f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590430"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfocount-method"></a><span data-ttu-id="cdda7-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="cdda7-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount Method</span></span>
<span data-ttu-id="cdda7-103">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="cdda7-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdda7-104">语法</span><span class="sxs-lookup"><span data-stu-id="cdda7-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfoCount(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdda7-105">参数</span><span class="sxs-lookup"><span data-stu-id="cdda7-105">Parameters</span></span>  
  
|<span data-ttu-id="cdda7-106">参数</span><span class="sxs-lookup"><span data-stu-id="cdda7-106">Parameter</span></span>|<span data-ttu-id="cdda7-107">描述</span><span class="sxs-lookup"><span data-stu-id="cdda7-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="cdda7-108">返回值</span><span class="sxs-lookup"><span data-stu-id="cdda7-108">Return Value</span></span>  
 <span data-ttu-id="cdda7-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="cdda7-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdda7-110">要求</span><span class="sxs-lookup"><span data-stu-id="cdda7-110">Requirements</span></span>  
 <span data-ttu-id="cdda7-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cdda7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdda7-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdda7-112">See also</span></span>
- [<span data-ttu-id="cdda7-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="cdda7-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
