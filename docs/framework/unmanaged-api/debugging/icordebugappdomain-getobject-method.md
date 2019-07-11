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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1201ac0dca9cbd48c24b2621eba079ae672fd310
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737853"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="9c60a-102">ICorDebugAppDomain::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="9c60a-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="9c60a-103">获取对公共语言运行时 (CLR) 应用程序域的接口指针。</span><span class="sxs-lookup"><span data-stu-id="9c60a-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c60a-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c60a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c60a-105">参数</span><span class="sxs-lookup"><span data-stu-id="9c60a-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="9c60a-106">[out]指向一个 ICorDebugValue 接口对象，表示 CLR 应用程序域的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9c60a-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c60a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="9c60a-107">Return Value</span></span>  
 <span data-ttu-id="9c60a-108">如果托管<xref:System.AppDomain?displayProperty=nameWithType>尚未为此应用程序域已构造对象，该方法返回`S_FALSE`，并将`NULL`中`*ppObject`。</span><span class="sxs-lookup"><span data-stu-id="9c60a-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c60a-109">备注</span><span class="sxs-lookup"><span data-stu-id="9c60a-109">Remarks</span></span>  
 <span data-ttu-id="9c60a-110">在进程中的每个应用程序域可能具有托管<xref:System.AppDomain?displayProperty=nameWithType>表示它在运行时中的对象。</span><span class="sxs-lookup"><span data-stu-id="9c60a-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="9c60a-111">此函数获取对应于此托管 ICorDebugValue 接口对象<xref:System.AppDomain?displayProperty=nameWithType>对象。</span><span class="sxs-lookup"><span data-stu-id="9c60a-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c60a-112">要求</span><span class="sxs-lookup"><span data-stu-id="9c60a-112">Requirements</span></span>  
 <span data-ttu-id="9c60a-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c60a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c60a-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c60a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c60a-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c60a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c60a-116">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c60a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
