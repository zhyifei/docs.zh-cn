---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bac541909e07aadff06006fba8c3cfcf4dc5465
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486220"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="5cf4e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="5cf4e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="5cf4e-103">定义一组异步等待当前方法中的操作。</span><span class="sxs-lookup"><span data-stu-id="5cf4e-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="5cf4e-104">每个 yield 偏移量与 await 表达式的返回指令，用于标识潜在 yield 相匹配。</span><span class="sxs-lookup"><span data-stu-id="5cf4e-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="5cf4e-105">每个`breakpointMethod` / `breakpointOffset`对告诉我们其中异步操作将恢复其可能在不同的方法。</span><span class="sxs-lookup"><span data-stu-id="5cf4e-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf4e-106">语法</span><span class="sxs-lookup"><span data-stu-id="5cf4e-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cf4e-107">参数</span><span class="sxs-lookup"><span data-stu-id="5cf4e-107">Parameters</span></span>  
  
|<span data-ttu-id="5cf4e-108">参数</span><span class="sxs-lookup"><span data-stu-id="5cf4e-108">Parameter</span></span>|<span data-ttu-id="5cf4e-109">描述</span><span class="sxs-lookup"><span data-stu-id="5cf4e-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="5cf4e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="5cf4e-110">Return Value</span></span>  
 <span data-ttu-id="5cf4e-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="5cf4e-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cf4e-112">要求</span><span class="sxs-lookup"><span data-stu-id="5cf4e-112">Requirements</span></span>  
 <span data-ttu-id="5cf4e-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5cf4e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf4e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cf4e-114">See also</span></span>
- [<span data-ttu-id="5cf4e-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="5cf4e-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
