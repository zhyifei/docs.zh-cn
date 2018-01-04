---
title: "ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c33403c48e6f395d8d0e10c7fddcea327d87529a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="bd4e3-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="bd4e3-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="bd4e3-103">定义一组异步等待在当前方法中的操作。</span><span class="sxs-lookup"><span data-stu-id="bd4e3-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="bd4e3-104">每个 yield 偏移量与 await 表达式的返回指令，用于标识潜在 yield 相匹配。</span><span class="sxs-lookup"><span data-stu-id="bd4e3-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="bd4e3-105">每个`breakpointMethod` / `breakpointOffset`对告诉我们其中异步操作将恢复，（这可以是不同的方法中。</span><span class="sxs-lookup"><span data-stu-id="bd4e3-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd4e3-106">语法</span><span class="sxs-lookup"><span data-stu-id="bd4e3-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd4e3-107">参数</span><span class="sxs-lookup"><span data-stu-id="bd4e3-107">Parameters</span></span>  
  
|<span data-ttu-id="bd4e3-108">参数</span><span class="sxs-lookup"><span data-stu-id="bd4e3-108">Parameter</span></span>|<span data-ttu-id="bd4e3-109">描述</span><span class="sxs-lookup"><span data-stu-id="bd4e3-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="bd4e3-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bd4e3-110">Return Value</span></span>  
 <span data-ttu-id="bd4e3-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="bd4e3-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd4e3-112">惠?</span><span class="sxs-lookup"><span data-stu-id="bd4e3-112">Requirements</span></span>  
 <span data-ttu-id="bd4e3-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bd4e3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd4e3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd4e3-114">See Also</span></span>  
 [<span data-ttu-id="bd4e3-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="bd4e3-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
