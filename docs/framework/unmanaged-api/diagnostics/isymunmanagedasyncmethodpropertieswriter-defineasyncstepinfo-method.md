---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ebd4bb1d674a27785ccbe5460a65fed764638ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435872"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="da04a-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="da04a-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="da04a-103">定义一组异步等待在当前方法中的操作。</span><span class="sxs-lookup"><span data-stu-id="da04a-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="da04a-104">每个 yield 偏移量与 await 表达式的返回指令，用于标识潜在 yield 相匹配。</span><span class="sxs-lookup"><span data-stu-id="da04a-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="da04a-105">每个`breakpointMethod` / `breakpointOffset`对告诉我们其中异步操作将恢复，（这可以是不同的方法中。</span><span class="sxs-lookup"><span data-stu-id="da04a-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da04a-106">语法</span><span class="sxs-lookup"><span data-stu-id="da04a-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da04a-107">参数</span><span class="sxs-lookup"><span data-stu-id="da04a-107">Parameters</span></span>  
  
|<span data-ttu-id="da04a-108">参数</span><span class="sxs-lookup"><span data-stu-id="da04a-108">Parameter</span></span>|<span data-ttu-id="da04a-109">描述</span><span class="sxs-lookup"><span data-stu-id="da04a-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="da04a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="da04a-110">Return Value</span></span>  
 <span data-ttu-id="da04a-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="da04a-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da04a-112">要求</span><span class="sxs-lookup"><span data-stu-id="da04a-112">Requirements</span></span>  
 <span data-ttu-id="da04a-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="da04a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da04a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="da04a-114">See Also</span></span>  
 [<span data-ttu-id="da04a-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="da04a-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
