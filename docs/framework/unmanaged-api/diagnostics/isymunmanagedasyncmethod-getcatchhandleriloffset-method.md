---
title: ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset 方法
ms.date: 03/30/2017
ms.assetid: d5f88656-433d-447c-b21c-2a12bed2e72a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cacf9333379566f80d270b172a1f3411bdc81cc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509761"
---
# <a name="isymunmanagedasyncmethodgetcatchhandleriloffset-method"></a><span data-ttu-id="ff9fc-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="ff9fc-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset Method</span></span>
<span data-ttu-id="ff9fc-103">请参阅[DefineCatchHandlerILOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ff9fc-103">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff9fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff9fc-104">Syntax</span></span>  
  
```idl  
HRESULT GetCatchHandlerILOffset(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff9fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff9fc-105">Parameters</span></span>  
  
|<span data-ttu-id="ff9fc-106">参数</span><span class="sxs-lookup"><span data-stu-id="ff9fc-106">Parameter</span></span>|<span data-ttu-id="ff9fc-107">描述</span><span class="sxs-lookup"><span data-stu-id="ff9fc-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="ff9fc-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ff9fc-108">Return Value</span></span>  
 <span data-ttu-id="ff9fc-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="ff9fc-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff9fc-110">要求</span><span class="sxs-lookup"><span data-stu-id="ff9fc-110">Requirements</span></span>  
 <span data-ttu-id="ff9fc-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ff9fc-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9fc-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff9fc-112">See also</span></span>
- [<span data-ttu-id="ff9fc-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="ff9fc-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
