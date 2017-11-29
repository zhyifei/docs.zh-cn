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
ms.openlocfilehash: 2e305ca13e419a40e9838a46a61fe7a435b7ce56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="073b2-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="073b2-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="073b2-103">定义一组异步等待在当前方法中的操作。</span><span class="sxs-lookup"><span data-stu-id="073b2-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="073b2-104">每个 yield 偏移量与 await 表达式的返回指令，用于标识潜在 yield 相匹配。</span><span class="sxs-lookup"><span data-stu-id="073b2-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="073b2-105">每个`breakpointMethod` / `breakpointOffset`对告诉我们其中异步操作将恢复，（这可以是不同的方法中。</span><span class="sxs-lookup"><span data-stu-id="073b2-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="073b2-106">语法</span><span class="sxs-lookup"><span data-stu-id="073b2-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="073b2-107">参数</span><span class="sxs-lookup"><span data-stu-id="073b2-107">Parameters</span></span>  
  
|<span data-ttu-id="073b2-108">参数</span><span class="sxs-lookup"><span data-stu-id="073b2-108">Parameter</span></span>|<span data-ttu-id="073b2-109">描述</span><span class="sxs-lookup"><span data-stu-id="073b2-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="073b2-110">返回值</span><span class="sxs-lookup"><span data-stu-id="073b2-110">Return Value</span></span>  
 <span data-ttu-id="073b2-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="073b2-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="073b2-112">要求</span><span class="sxs-lookup"><span data-stu-id="073b2-112">Requirements</span></span>  
 <span data-ttu-id="073b2-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="073b2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="073b2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="073b2-114">See Also</span></span>  
 [<span data-ttu-id="073b2-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="073b2-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
