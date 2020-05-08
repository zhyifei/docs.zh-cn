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
ms.openlocfilehash: a21f3b36e418bbde5dcb90f25a39dae03fde77c9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895215"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="f5a5b-102">ICorDebugAppDomain::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="f5a5b-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="f5a5b-103">获取指向公共语言运行时（CLR）应用程序域的接口指针。</span><span class="sxs-lookup"><span data-stu-id="f5a5b-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5a5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a5b-105">参数</span><span class="sxs-lookup"><span data-stu-id="f5a5b-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="f5a5b-106">弄指向表示 CLR 应用程序域的 ICorDebugValue 接口对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f5a5b-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5a5b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f5a5b-107">Return Value</span></span>  
 <span data-ttu-id="f5a5b-108">如果尚未为<xref:System.AppDomain?displayProperty=nameWithType>此应用程序域构造托管对象，则该方法将`S_FALSE`返回， `NULL`并`*ppObject`将放入。</span><span class="sxs-lookup"><span data-stu-id="f5a5b-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5a5b-109">备注</span><span class="sxs-lookup"><span data-stu-id="f5a5b-109">Remarks</span></span>  
 <span data-ttu-id="f5a5b-110">进程中的每个应用程序域在运行<xref:System.AppDomain?displayProperty=nameWithType>时中都可能有一个表示该对象的托管对象。</span><span class="sxs-lookup"><span data-stu-id="f5a5b-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="f5a5b-111">此函数获取对应于此托管<xref:System.AppDomain?displayProperty=nameWithType>对象的 ICorDebugValue 接口对象。</span><span class="sxs-lookup"><span data-stu-id="f5a5b-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a5b-112">要求</span><span class="sxs-lookup"><span data-stu-id="f5a5b-112">Requirements</span></span>  
 <span data-ttu-id="f5a5b-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5a5b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a5b-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5a5b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5a5b-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5a5b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5a5b-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a5b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
