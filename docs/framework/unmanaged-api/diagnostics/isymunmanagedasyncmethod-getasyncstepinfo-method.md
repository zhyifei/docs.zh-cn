---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 方法
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: e3c0d7b8eeded403ce8391cff00ee18dccc38ed5
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441885"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="bddbe-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="bddbe-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="bddbe-103">请参阅[DefineAsyncStepInfo 方法](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)。</span><span class="sxs-lookup"><span data-stu-id="bddbe-103">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bddbe-104">语法</span><span class="sxs-lookup"><span data-stu-id="bddbe-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bddbe-105">参数</span><span class="sxs-lookup"><span data-stu-id="bddbe-105">Parameters</span></span>  
  
|<span data-ttu-id="bddbe-106">参数</span><span class="sxs-lookup"><span data-stu-id="bddbe-106">Parameter</span></span>|<span data-ttu-id="bddbe-107">说明</span><span class="sxs-lookup"><span data-stu-id="bddbe-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="bddbe-108">返回值</span><span class="sxs-lookup"><span data-stu-id="bddbe-108">Return Value</span></span>  
 <span data-ttu-id="bddbe-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="bddbe-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bddbe-110">要求</span><span class="sxs-lookup"><span data-stu-id="bddbe-110">Requirements</span></span>  
 <span data-ttu-id="bddbe-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="bddbe-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bddbe-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bddbe-112">See also</span></span>

- [<span data-ttu-id="bddbe-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="bddbe-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
