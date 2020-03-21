---
title: 继承来自函数（非托管 API 引用）
description: 继承 From 函数确定类或实例是否派生自特定的父类。
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
ms.openlocfilehash: c735c01c45beda8a1ba988a5c580e6b04ae46312
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174935"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="b8170-103">InheritsFrom 函数</span><span class="sxs-lookup"><span data-stu-id="b8170-103">InheritsFrom function</span></span>
<span data-ttu-id="b8170-104">确定当前类或实例是否派生自指定的父类。</span><span class="sxs-lookup"><span data-stu-id="b8170-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b8170-105">语法</span><span class="sxs-lookup"><span data-stu-id="b8170-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a><span data-ttu-id="b8170-106">parameters</span><span class="sxs-lookup"><span data-stu-id="b8170-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b8170-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="b8170-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b8170-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="b8170-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="b8170-109">[在]类的名称。</span><span class="sxs-lookup"><span data-stu-id="b8170-109">[in] The name of the class.</span></span> <span data-ttu-id="b8170-110">`wszAncestor`必须指向有效的`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="b8170-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b8170-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b8170-111">Return value</span></span>

<span data-ttu-id="b8170-112">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="b8170-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b8170-113">一直</span><span class="sxs-lookup"><span data-stu-id="b8170-113">Constant</span></span>  |<span data-ttu-id="b8170-114">值</span><span class="sxs-lookup"><span data-stu-id="b8170-114">Value</span></span>  |<span data-ttu-id="b8170-115">说明</span><span class="sxs-lookup"><span data-stu-id="b8170-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b8170-116">0</span><span class="sxs-lookup"><span data-stu-id="b8170-116">0</span></span> | <span data-ttu-id="b8170-117">当前对象从`wszAncestor`继承。</span><span class="sxs-lookup"><span data-stu-id="b8170-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="b8170-118">1</span><span class="sxs-lookup"><span data-stu-id="b8170-118">1</span></span> | <span data-ttu-id="b8170-119">当前对象不从`wszAncestor`继承。</span><span class="sxs-lookup"><span data-stu-id="b8170-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b8170-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b8170-120">0x80041008</span></span> | <span data-ttu-id="b8170-121">`wszAncestor` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="b8170-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b8170-122">备注</span><span class="sxs-lookup"><span data-stu-id="b8170-122">Remarks</span></span>

<span data-ttu-id="b8170-123">此函数包装对[IWbem ClassObject 的调用：：继承方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom)。</span><span class="sxs-lookup"><span data-stu-id="b8170-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8170-124">要求</span><span class="sxs-lookup"><span data-stu-id="b8170-124">Requirements</span></span>  
 <span data-ttu-id="b8170-125">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8170-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8170-126">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b8170-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b8170-127">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b8170-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8170-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8170-128">See also</span></span>

- [<span data-ttu-id="b8170-129">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="b8170-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
