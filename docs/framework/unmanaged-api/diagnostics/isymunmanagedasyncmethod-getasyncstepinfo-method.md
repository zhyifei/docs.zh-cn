---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 方法
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34792ddc7d32c89f6572a48e4636a63881611b88
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473547"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="8197b-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="8197b-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="8197b-103">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="8197b-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8197b-104">语法</span><span class="sxs-lookup"><span data-stu-id="8197b-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8197b-105">参数</span><span class="sxs-lookup"><span data-stu-id="8197b-105">Parameters</span></span>  
  
|<span data-ttu-id="8197b-106">参数</span><span class="sxs-lookup"><span data-stu-id="8197b-106">Parameter</span></span>|<span data-ttu-id="8197b-107">描述</span><span class="sxs-lookup"><span data-stu-id="8197b-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="8197b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="8197b-108">Return Value</span></span>  
 <span data-ttu-id="8197b-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="8197b-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8197b-110">要求</span><span class="sxs-lookup"><span data-stu-id="8197b-110">Requirements</span></span>  
 <span data-ttu-id="8197b-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8197b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8197b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8197b-112">See also</span></span>
- [<span data-ttu-id="8197b-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="8197b-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
