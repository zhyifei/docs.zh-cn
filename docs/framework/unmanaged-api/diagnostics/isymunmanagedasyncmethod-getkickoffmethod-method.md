---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f20039318d6e1230ccc0fbd203fc44686806bb2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604465"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="ba35f-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="ba35f-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="ba35f-103">请参阅[DefineKickoffMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ba35f-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba35f-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba35f-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba35f-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba35f-105">Parameters</span></span>  
  
|<span data-ttu-id="ba35f-106">参数</span><span class="sxs-lookup"><span data-stu-id="ba35f-106">Parameter</span></span>|<span data-ttu-id="ba35f-107">描述</span><span class="sxs-lookup"><span data-stu-id="ba35f-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="ba35f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ba35f-108">Return Value</span></span>  
 <span data-ttu-id="ba35f-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="ba35f-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba35f-110">要求</span><span class="sxs-lookup"><span data-stu-id="ba35f-110">Requirements</span></span>  
 <span data-ttu-id="ba35f-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ba35f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba35f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba35f-112">See also</span></span>
- [<span data-ttu-id="ba35f-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="ba35f-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
