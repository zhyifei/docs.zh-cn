---
title: ICorDebugAppDomain::GetObject 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
ms.openlocfilehash: f2c881603cfa0e4b3d2dc8d1e996631b51d1e850
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134704"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="e4525-102">ICorDebugAppDomain::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="e4525-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="e4525-103">获取指向公共语言运行时（CLR）应用程序域的接口指针。</span><span class="sxs-lookup"><span data-stu-id="e4525-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4525-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4525-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4525-105">参数</span><span class="sxs-lookup"><span data-stu-id="e4525-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="e4525-106">弄指向表示 CLR 应用程序域的 ICorDebugValue 接口对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="e4525-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4525-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e4525-107">Return Value</span></span>  
 <span data-ttu-id="e4525-108">如果尚未为此应用程序域构造托管的 <xref:System.AppDomain?displayProperty=nameWithType> 对象，则该方法将返回 `S_FALSE` 并将 `NULL` 放置在 `*ppObject`中。</span><span class="sxs-lookup"><span data-stu-id="e4525-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4525-109">备注</span><span class="sxs-lookup"><span data-stu-id="e4525-109">Remarks</span></span>  
 <span data-ttu-id="e4525-110">进程中的每个应用程序域在运行时中都可能有一个托管的 <xref:System.AppDomain?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="e4525-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="e4525-111">此函数获取对应于此托管 <xref:System.AppDomain?displayProperty=nameWithType> 对象的 ICorDebugValue 接口对象。</span><span class="sxs-lookup"><span data-stu-id="e4525-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4525-112">要求</span><span class="sxs-lookup"><span data-stu-id="e4525-112">Requirements</span></span>  
 <span data-ttu-id="e4525-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4525-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4525-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4525-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4525-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4525-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4525-116">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4525-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
