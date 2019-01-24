---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 方法
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa87188765450e84fc2417be8530ff43c88c237c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666223"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="d5afa-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="d5afa-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="d5afa-103">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d5afa-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5afa-104">语法</span><span class="sxs-lookup"><span data-stu-id="d5afa-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5afa-105">参数</span><span class="sxs-lookup"><span data-stu-id="d5afa-105">Parameters</span></span>  
  
|<span data-ttu-id="d5afa-106">参数</span><span class="sxs-lookup"><span data-stu-id="d5afa-106">Parameter</span></span>|<span data-ttu-id="d5afa-107">描述</span><span class="sxs-lookup"><span data-stu-id="d5afa-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="d5afa-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d5afa-108">Return Value</span></span>  
 <span data-ttu-id="d5afa-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="d5afa-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5afa-110">要求</span><span class="sxs-lookup"><span data-stu-id="d5afa-110">Requirements</span></span>  
 <span data-ttu-id="d5afa-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d5afa-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5afa-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5afa-112">See also</span></span>
- [<span data-ttu-id="d5afa-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="d5afa-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
