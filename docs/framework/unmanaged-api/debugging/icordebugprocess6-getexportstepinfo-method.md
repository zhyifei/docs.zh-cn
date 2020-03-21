---
title: ICorDebugProcess6::GetExportStepInfo 方法
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 6580fdaacaea17fcf886bfd7ac5e236925acf453
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178528"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="753f4-102">ICorDebugProcess6::GetExportStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="753f4-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="753f4-103">提供运行时导出功能信息以帮助单步调试托管代码。</span><span class="sxs-lookup"><span data-stu-id="753f4-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="753f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="753f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="753f4-105">parameters</span><span class="sxs-lookup"><span data-stu-id="753f4-105">Parameters</span></span>  
 <span data-ttu-id="753f4-106">psz导出名</span><span class="sxs-lookup"><span data-stu-id="753f4-106">pszExportName</span></span>  
 <span data-ttu-id="753f4-107">[输入] 如 PE 导出表中所写的运行时间导出函数名。</span><span class="sxs-lookup"><span data-stu-id="753f4-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="753f4-108">调用类型</span><span class="sxs-lookup"><span data-stu-id="753f4-108">invokeKind</span></span>  
 <span data-ttu-id="753f4-109">[出]指向[CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md)枚举成员的指针，用于描述导出的函数将如何调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="753f4-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="753f4-110">调用目的</span><span class="sxs-lookup"><span data-stu-id="753f4-110">invokePurpose</span></span>  
 <span data-ttu-id="753f4-111">[出]指向[CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md)枚举成员的指针，用于描述导出函数将调用托管代码的原因。</span><span class="sxs-lookup"><span data-stu-id="753f4-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="753f4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="753f4-112">Return Value</span></span>  
 <span data-ttu-id="753f4-113">该方法可以返回下表所列的值。</span><span class="sxs-lookup"><span data-stu-id="753f4-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="753f4-114">返回值</span><span class="sxs-lookup"><span data-stu-id="753f4-114">Return value</span></span>|<span data-ttu-id="753f4-115">说明</span><span class="sxs-lookup"><span data-stu-id="753f4-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="753f4-116">方法调用成功。</span><span class="sxs-lookup"><span data-stu-id="753f4-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="753f4-117">`pInvokeKind`或`pInvokePurpose`**为 null**。</span><span class="sxs-lookup"><span data-stu-id="753f4-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="753f4-118">其他失败 `HRESULT` 值。</span><span class="sxs-lookup"><span data-stu-id="753f4-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="753f4-119">根据需要。</span><span class="sxs-lookup"><span data-stu-id="753f4-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="753f4-120">备注</span><span class="sxs-lookup"><span data-stu-id="753f4-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="753f4-121">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="753f4-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="753f4-122">要求</span><span class="sxs-lookup"><span data-stu-id="753f4-122">Requirements</span></span>  
 <span data-ttu-id="753f4-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="753f4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="753f4-124">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="753f4-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="753f4-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="753f4-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="753f4-126">**.NET 框架版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="753f4-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753f4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="753f4-127">See also</span></span>

- [<span data-ttu-id="753f4-128">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="753f4-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="753f4-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="753f4-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
