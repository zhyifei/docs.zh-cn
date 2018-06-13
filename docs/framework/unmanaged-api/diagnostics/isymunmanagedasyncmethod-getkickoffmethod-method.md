---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2f055dc19bf7f40036283102d8cc4549555b992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424763"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="532ec-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="532ec-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="532ec-103">请参阅[DefineKickoffMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="532ec-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532ec-104">语法</span><span class="sxs-lookup"><span data-stu-id="532ec-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="532ec-105">参数</span><span class="sxs-lookup"><span data-stu-id="532ec-105">Parameters</span></span>  
  
|<span data-ttu-id="532ec-106">参数</span><span class="sxs-lookup"><span data-stu-id="532ec-106">Parameter</span></span>|<span data-ttu-id="532ec-107">描述</span><span class="sxs-lookup"><span data-stu-id="532ec-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="532ec-108">返回值</span><span class="sxs-lookup"><span data-stu-id="532ec-108">Return Value</span></span>  
 <span data-ttu-id="532ec-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="532ec-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="532ec-110">要求</span><span class="sxs-lookup"><span data-stu-id="532ec-110">Requirements</span></span>  
 <span data-ttu-id="532ec-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="532ec-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532ec-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="532ec-112">See Also</span></span>  
 [<span data-ttu-id="532ec-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="532ec-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
