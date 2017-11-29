---
title: "ICorDebugAppDomain::GetObject 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetObject
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c4f923d8e9bf9762d5208dd6e9be527a50a688b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="78f73-102">ICorDebugAppDomain::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="78f73-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="78f73-103">公共语言运行时 (CLR) 应用程序域中获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="78f73-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f73-104">语法</span><span class="sxs-lookup"><span data-stu-id="78f73-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78f73-105">参数</span><span class="sxs-lookup"><span data-stu-id="78f73-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="78f73-106">[out]指向一个 ICorDebugValue 接口对象，表示 CLR 应用程序域的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="78f73-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78f73-107">返回值</span><span class="sxs-lookup"><span data-stu-id="78f73-107">Return Value</span></span>  
 <span data-ttu-id="78f73-108">如果托管<xref:System.AppDomain?displayProperty=nameWithType>对象尚未为此应用程序域中构造，该方法返回`S_FALSE`并放置`NULL`中`*ppObject`。</span><span class="sxs-lookup"><span data-stu-id="78f73-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78f73-109">备注</span><span class="sxs-lookup"><span data-stu-id="78f73-109">Remarks</span></span>  
 <span data-ttu-id="78f73-110">每个应用程序域的过程中可能具有托管<xref:System.AppDomain?displayProperty=nameWithType>表示它的运行时中的对象。</span><span class="sxs-lookup"><span data-stu-id="78f73-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="78f73-111">此函数获取对应于此管理的 ICorDebugValue 接口对象<xref:System.AppDomain?displayProperty=nameWithType>对象。</span><span class="sxs-lookup"><span data-stu-id="78f73-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f73-112">要求</span><span class="sxs-lookup"><span data-stu-id="78f73-112">Requirements</span></span>  
 <span data-ttu-id="78f73-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="78f73-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78f73-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78f73-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78f73-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78f73-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78f73-116">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78f73-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
