---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 方法
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7c72d0766580f9aa3aa678aacd872b804172a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131425"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="55eab-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="55eab-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="55eab-103">请参阅[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="55eab-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55eab-104">语法</span><span class="sxs-lookup"><span data-stu-id="55eab-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55eab-105">参数</span><span class="sxs-lookup"><span data-stu-id="55eab-105">Parameters</span></span>  
  
|<span data-ttu-id="55eab-106">参数</span><span class="sxs-lookup"><span data-stu-id="55eab-106">Parameter</span></span>|<span data-ttu-id="55eab-107">描述</span><span class="sxs-lookup"><span data-stu-id="55eab-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="55eab-108">返回值</span><span class="sxs-lookup"><span data-stu-id="55eab-108">Return Value</span></span>  
 <span data-ttu-id="55eab-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="55eab-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55eab-110">要求</span><span class="sxs-lookup"><span data-stu-id="55eab-110">Requirements</span></span>  
 <span data-ttu-id="55eab-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="55eab-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55eab-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="55eab-112">See also</span></span>

- [<span data-ttu-id="55eab-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="55eab-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
