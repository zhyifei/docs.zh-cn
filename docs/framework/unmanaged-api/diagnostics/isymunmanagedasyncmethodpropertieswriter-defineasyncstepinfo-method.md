---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: 59e3a95a4d2573263600da60b4f852caa361138e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129201"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="09a83-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="09a83-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="09a83-103">在当前方法中定义一组异步等待操作。</span><span class="sxs-lookup"><span data-stu-id="09a83-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="09a83-104">每个 yield 偏移均与 await 的返回指令匹配，确定潜在的收益率。</span><span class="sxs-lookup"><span data-stu-id="09a83-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="09a83-105">每个 `breakpointMethod`/`breakpointOffset` 对都告诉我们异步操作的恢复位置，这可能是在不同的方法中。</span><span class="sxs-lookup"><span data-stu-id="09a83-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09a83-106">语法</span><span class="sxs-lookup"><span data-stu-id="09a83-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09a83-107">参数</span><span class="sxs-lookup"><span data-stu-id="09a83-107">Parameters</span></span>  
  
|<span data-ttu-id="09a83-108">参数</span><span class="sxs-lookup"><span data-stu-id="09a83-108">Parameter</span></span>|<span data-ttu-id="09a83-109">描述</span><span class="sxs-lookup"><span data-stu-id="09a83-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="09a83-110">返回值</span><span class="sxs-lookup"><span data-stu-id="09a83-110">Return Value</span></span>  
 <span data-ttu-id="09a83-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="09a83-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09a83-112">要求</span><span class="sxs-lookup"><span data-stu-id="09a83-112">Requirements</span></span>  
 <span data-ttu-id="09a83-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="09a83-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a83-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="09a83-114">See also</span></span>

- [<span data-ttu-id="09a83-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="09a83-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
