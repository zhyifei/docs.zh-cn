---
title: ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset 方法
ms.date: 03/30/2017
ms.assetid: d5f88656-433d-447c-b21c-2a12bed2e72a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 527e686eb0c354c3a1ebba36772e30211e995ab2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425348"
---
# <a name="isymunmanagedasyncmethodgetcatchhandleriloffset-method"></a><span data-ttu-id="a7c4a-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="a7c4a-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset Method</span></span>
<span data-ttu-id="a7c4a-103">请参阅[DefineCatchHandlerILOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a7c4a-103">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7c4a-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7c4a-104">Syntax</span></span>  
  
```idl  
HRESULT GetCatchHandlerILOffset(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7c4a-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7c4a-105">Parameters</span></span>  
  
|<span data-ttu-id="a7c4a-106">参数</span><span class="sxs-lookup"><span data-stu-id="a7c4a-106">Parameter</span></span>|<span data-ttu-id="a7c4a-107">描述</span><span class="sxs-lookup"><span data-stu-id="a7c4a-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="a7c4a-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a7c4a-108">Return Value</span></span>  
 <span data-ttu-id="a7c4a-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="a7c4a-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7c4a-110">要求</span><span class="sxs-lookup"><span data-stu-id="a7c4a-110">Requirements</span></span>  
 <span data-ttu-id="a7c4a-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a7c4a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c4a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7c4a-112">See Also</span></span>  
 [<span data-ttu-id="a7c4a-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="a7c4a-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
