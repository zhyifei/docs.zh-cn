---
title: ICorDebugProcess6::GetExportStepInfo 方法
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a891e6d65d159875f5607ac33b0668414cb380
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137210"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="2bbc9-102">ICorDebugProcess6::GetExportStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="2bbc9-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="2bbc9-103">提供运行时导出功能信息以帮助单步调试托管代码。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bbc9-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bbc9-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bbc9-105">参数</span><span class="sxs-lookup"><span data-stu-id="2bbc9-105">Parameters</span></span>  
 <span data-ttu-id="2bbc9-106">psz导出名</span><span class="sxs-lookup"><span data-stu-id="2bbc9-106">pszExportName</span></span>  
 <span data-ttu-id="2bbc9-107">[输入] 如 PE 导出表中所写的运行时间导出函数名。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="2bbc9-108">调用类型</span><span class="sxs-lookup"><span data-stu-id="2bbc9-108">invokeKind</span></span>  
 <span data-ttu-id="2bbc9-109">[out]指向成员的指针[CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)描述导出的函数将如何调用托管的代码的枚举。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="2bbc9-110">调用目的</span><span class="sxs-lookup"><span data-stu-id="2bbc9-110">invokePurpose</span></span>  
 <span data-ttu-id="2bbc9-111">[out]指向成员的指针[CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)描述为何导出的函数将调用托管的代码的枚举。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bbc9-112">返回值</span><span class="sxs-lookup"><span data-stu-id="2bbc9-112">Return Value</span></span>  
 <span data-ttu-id="2bbc9-113">该方法可以返回下表所列的值。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="2bbc9-114">返回值</span><span class="sxs-lookup"><span data-stu-id="2bbc9-114">Return value</span></span>|<span data-ttu-id="2bbc9-115">描述</span><span class="sxs-lookup"><span data-stu-id="2bbc9-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="2bbc9-116">方法调用成功。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-116">The method call was successful.</span></span>|  
|`E_POINTER`|`pInvokeKind` <span data-ttu-id="2bbc9-117">或`pInvokePurpose`是**null**。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-117">or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="2bbc9-118">其他失败 `HRESULT` 值。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="2bbc9-119">根据需要。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bbc9-120">备注</span><span class="sxs-lookup"><span data-stu-id="2bbc9-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bbc9-121">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bbc9-122">要求</span><span class="sxs-lookup"><span data-stu-id="2bbc9-122">Requirements</span></span>  
 <span data-ttu-id="2bbc9-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bbc9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bbc9-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bbc9-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bbc9-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bbc9-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2bbc9-126">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2bbc9-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2bbc9-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bbc9-127">See also</span></span>

- [<span data-ttu-id="2bbc9-128">“ICor调试进程6”接口</span><span class="sxs-lookup"><span data-stu-id="2bbc9-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="2bbc9-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="2bbc9-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
