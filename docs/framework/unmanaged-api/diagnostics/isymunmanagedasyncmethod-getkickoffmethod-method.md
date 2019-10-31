---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
ms.openlocfilehash: 58daec30b4cbae9cfaab27d4ce76521ba839cf83
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139843"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="4bd1e-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="4bd1e-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="4bd1e-103">请参阅[DefineKickoffMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd1e-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd1e-104">语法</span><span class="sxs-lookup"><span data-stu-id="4bd1e-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bd1e-105">参数</span><span class="sxs-lookup"><span data-stu-id="4bd1e-105">Parameters</span></span>  
  
|<span data-ttu-id="4bd1e-106">参数</span><span class="sxs-lookup"><span data-stu-id="4bd1e-106">Parameter</span></span>|<span data-ttu-id="4bd1e-107">描述</span><span class="sxs-lookup"><span data-stu-id="4bd1e-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="4bd1e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4bd1e-108">Return Value</span></span>  
 <span data-ttu-id="4bd1e-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="4bd1e-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd1e-110">要求</span><span class="sxs-lookup"><span data-stu-id="4bd1e-110">Requirements</span></span>  
 <span data-ttu-id="4bd1e-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="4bd1e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd1e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bd1e-112">See also</span></span>

- [<span data-ttu-id="4bd1e-113">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="4bd1e-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
