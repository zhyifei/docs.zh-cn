---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 方法
ms.date: 03/30/2017
ms.assetid: 32a4e084-09b2-4946-a4a7-19a1fed9f7cc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2904fe91f223b528450684d8de2f70dba48fc792
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425059"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfocount-method"></a><span data-ttu-id="a8432-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="a8432-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount Method</span></span>
<span data-ttu-id="a8432-103">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a8432-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8432-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8432-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfoCount(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8432-105">参数</span><span class="sxs-lookup"><span data-stu-id="a8432-105">Parameters</span></span>  
  
|<span data-ttu-id="a8432-106">参数</span><span class="sxs-lookup"><span data-stu-id="a8432-106">Parameter</span></span>|<span data-ttu-id="a8432-107">描述</span><span class="sxs-lookup"><span data-stu-id="a8432-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="a8432-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a8432-108">Return Value</span></span>  
 <span data-ttu-id="a8432-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="a8432-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8432-110">要求</span><span class="sxs-lookup"><span data-stu-id="a8432-110">Requirements</span></span>  
 <span data-ttu-id="a8432-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a8432-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8432-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8432-112">See Also</span></span>  
 [<span data-ttu-id="a8432-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="a8432-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
