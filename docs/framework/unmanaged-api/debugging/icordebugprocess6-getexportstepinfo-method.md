---
title: "ICorDebugProcess6::GetExportStepInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3c69bbc904f54636e56be6d235d1070b9fecf1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="71352-102">ICorDebugProcess6::GetExportStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="71352-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="71352-103">提供运行时导出功能信息以帮助单步调试托管代码。</span><span class="sxs-lookup"><span data-stu-id="71352-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71352-104">语法</span><span class="sxs-lookup"><span data-stu-id="71352-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71352-105">参数</span><span class="sxs-lookup"><span data-stu-id="71352-105">Parameters</span></span>  
 <span data-ttu-id="71352-106">psz导出名</span><span class="sxs-lookup"><span data-stu-id="71352-106">pszExportName</span></span>  
 <span data-ttu-id="71352-107">[输入] 如 PE 导出表中所写的运行时间导出函数名。</span><span class="sxs-lookup"><span data-stu-id="71352-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="71352-108">调用类型</span><span class="sxs-lookup"><span data-stu-id="71352-108">invokeKind</span></span>  
 <span data-ttu-id="71352-109">[out]指向的成员的指针[CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)描述导出的函数将如何调用托管的代码的枚举。</span><span class="sxs-lookup"><span data-stu-id="71352-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="71352-110">调用目的</span><span class="sxs-lookup"><span data-stu-id="71352-110">invokePurpose</span></span>  
 <span data-ttu-id="71352-111">[out]指向的成员的指针[CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)描述导出的函数将如何调用托管的代码的枚举。</span><span class="sxs-lookup"><span data-stu-id="71352-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71352-112">返回值</span><span class="sxs-lookup"><span data-stu-id="71352-112">Return Value</span></span>  
 <span data-ttu-id="71352-113">该方法可以返回下表所列的值。</span><span class="sxs-lookup"><span data-stu-id="71352-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="71352-114">返回值</span><span class="sxs-lookup"><span data-stu-id="71352-114">Return value</span></span>|<span data-ttu-id="71352-115">描述</span><span class="sxs-lookup"><span data-stu-id="71352-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="71352-116">方法调用成功。</span><span class="sxs-lookup"><span data-stu-id="71352-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="71352-117">`pInvokeKind`或`pInvokePurpose`是**null**。</span><span class="sxs-lookup"><span data-stu-id="71352-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="71352-118">其他失败 `HRESULT` 值。</span><span class="sxs-lookup"><span data-stu-id="71352-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="71352-119">根据需要。</span><span class="sxs-lookup"><span data-stu-id="71352-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71352-120">备注</span><span class="sxs-lookup"><span data-stu-id="71352-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71352-121">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="71352-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71352-122">惠?</span><span class="sxs-lookup"><span data-stu-id="71352-122">Requirements</span></span>  
 <span data-ttu-id="71352-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71352-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71352-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71352-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71352-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71352-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71352-126">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71352-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71352-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="71352-127">See Also</span></span>  
 [<span data-ttu-id="71352-128">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="71352-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="71352-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="71352-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
