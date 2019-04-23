---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4599d41336778db8ce8dcf3ac567e4e2cc8833e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174936"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="3ba1b-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="3ba1b-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="3ba1b-103">请参阅[DefineKickoffMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3ba1b-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ba1b-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ba1b-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ba1b-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ba1b-105">Parameters</span></span>  
  
|<span data-ttu-id="3ba1b-106">参数</span><span class="sxs-lookup"><span data-stu-id="3ba1b-106">Parameter</span></span>|<span data-ttu-id="3ba1b-107">描述</span><span class="sxs-lookup"><span data-stu-id="3ba1b-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="3ba1b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3ba1b-108">Return Value</span></span>  
 <span data-ttu-id="3ba1b-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="3ba1b-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ba1b-110">要求</span><span class="sxs-lookup"><span data-stu-id="3ba1b-110">Requirements</span></span>  
 <span data-ttu-id="3ba1b-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3ba1b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba1b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ba1b-112">See also</span></span>

- [<span data-ttu-id="3ba1b-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="3ba1b-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
