---
title: InheritsFrom 函数（非托管 API 参考）
description: InheritsFrom 函数确定类或实例是否从特定的父类派生。
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c32c54ec56ea0fe4f4039ca6438a91338edbadb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798453"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="c3b4e-103">InheritsFrom 函数</span><span class="sxs-lookup"><span data-stu-id="c3b4e-103">InheritsFrom function</span></span>
<span data-ttu-id="c3b4e-104">确定当前类或实例是否派生自指定的父类。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c3b4e-105">语法</span><span class="sxs-lookup"><span data-stu-id="c3b4e-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="c3b4e-106">参数</span><span class="sxs-lookup"><span data-stu-id="c3b4e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c3b4e-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c3b4e-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="c3b4e-109">中类的名称。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-109">[in] The name of the class.</span></span> <span data-ttu-id="c3b4e-110">`wszAncestor`必须指向有效`LPCWSTR`的。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c3b4e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="c3b4e-111">Return value</span></span>

<span data-ttu-id="c3b4e-112">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="c3b4e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c3b4e-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="c3b4e-113">Constant</span></span>  |<span data-ttu-id="c3b4e-114">值</span><span class="sxs-lookup"><span data-stu-id="c3b4e-114">Value</span></span>  |<span data-ttu-id="c3b4e-115">Description</span><span class="sxs-lookup"><span data-stu-id="c3b4e-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c3b4e-116">0</span><span class="sxs-lookup"><span data-stu-id="c3b4e-116">0</span></span> | <span data-ttu-id="c3b4e-117">当前对象继承自`wszAncestor`。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="c3b4e-118">1</span><span class="sxs-lookup"><span data-stu-id="c3b4e-118">1</span></span> | <span data-ttu-id="c3b4e-119">当前的对象不是从`wszAncestor`继承的。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c3b4e-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c3b4e-120">0x80041008</span></span> | <span data-ttu-id="c3b4e-121">`wszAncestor` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c3b4e-122">备注</span><span class="sxs-lookup"><span data-stu-id="c3b4e-122">Remarks</span></span>

<span data-ttu-id="c3b4e-123">此函数包装对[IWbemClassObject：： InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c3b4e-124">要求</span><span class="sxs-lookup"><span data-stu-id="c3b4e-124">Requirements</span></span>  
 <span data-ttu-id="c3b4e-125">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3b4e-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3b4e-126">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c3b4e-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c3b4e-127">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c3b4e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b4e-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3b4e-128">See also</span></span>

- [<span data-ttu-id="c3b4e-129">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="c3b4e-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
