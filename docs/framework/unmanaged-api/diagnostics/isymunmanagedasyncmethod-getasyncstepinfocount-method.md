---
title: "ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 32a4e084-09b2-4946-a4a7-19a1fed9f7cc
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b2431662caa41c67746da7e21591c743896c161
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfocount-method"></a><span data-ttu-id="ddf98-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="ddf98-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount Method</span></span>
<span data-ttu-id="ddf98-103">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ddf98-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddf98-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddf98-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfoCount(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddf98-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddf98-105">Parameters</span></span>  
  
|<span data-ttu-id="ddf98-106">参数</span><span class="sxs-lookup"><span data-stu-id="ddf98-106">Parameter</span></span>|<span data-ttu-id="ddf98-107">描述</span><span class="sxs-lookup"><span data-stu-id="ddf98-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="ddf98-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ddf98-108">Return Value</span></span>  
 <span data-ttu-id="ddf98-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="ddf98-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddf98-110">要求</span><span class="sxs-lookup"><span data-stu-id="ddf98-110">Requirements</span></span>  
 <span data-ttu-id="ddf98-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ddf98-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf98-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddf98-112">See Also</span></span>  
 [<span data-ttu-id="ddf98-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="ddf98-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
