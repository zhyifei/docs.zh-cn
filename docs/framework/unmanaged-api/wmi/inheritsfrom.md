---
title: InheritsFrom 函数 （非托管 API 参考）
description: InheritsFrom 函数将确定从特定父类是否派生的类或实例。
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
ms.openlocfilehash: 4784e22d5a3eec031fbee00441958a62d66b52df
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44222102"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="3a8e5-103">InheritsFrom 函数</span><span class="sxs-lookup"><span data-stu-id="3a8e5-103">InheritsFrom function</span></span>
<span data-ttu-id="3a8e5-104">确定当前类或实例是否派生自指定的父类。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="3a8e5-105">语法</span><span class="sxs-lookup"><span data-stu-id="3a8e5-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="3a8e5-106">参数</span><span class="sxs-lookup"><span data-stu-id="3a8e5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3a8e5-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3a8e5-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="3a8e5-109">[in]类的名称。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-109">[in] The name of the class.</span></span> <span data-ttu-id="3a8e5-110">`wszAncestor` 必须指向有效`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3a8e5-111">返回值</span><span class="sxs-lookup"><span data-stu-id="3a8e5-111">Return value</span></span>

<span data-ttu-id="3a8e5-112">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="3a8e5-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3a8e5-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="3a8e5-113">Constant</span></span>  |<span data-ttu-id="3a8e5-114">“值”</span><span class="sxs-lookup"><span data-stu-id="3a8e5-114">Value</span></span>  |<span data-ttu-id="3a8e5-115">描述</span><span class="sxs-lookup"><span data-stu-id="3a8e5-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3a8e5-116">0</span><span class="sxs-lookup"><span data-stu-id="3a8e5-116">0</span></span> | <span data-ttu-id="3a8e5-117">当前对象继承`wszAncestor`。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="3a8e5-118">1</span><span class="sxs-lookup"><span data-stu-id="3a8e5-118">1</span></span> | <span data-ttu-id="3a8e5-119">当前对象不会继承从`wszAncestor`。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3a8e5-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3a8e5-120">0x80041008</span></span> | <span data-ttu-id="3a8e5-121">`wszAncestor` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3a8e5-122">备注</span><span class="sxs-lookup"><span data-stu-id="3a8e5-122">Remarks</span></span>

<span data-ttu-id="3a8e5-123">此函数包装对的调用[IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom)方法。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a8e5-124">要求</span><span class="sxs-lookup"><span data-stu-id="3a8e5-124">Requirements</span></span>  
 <span data-ttu-id="3a8e5-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8e5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a8e5-126">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3a8e5-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3a8e5-127">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3a8e5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8e5-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a8e5-128">See also</span></span>  
[<span data-ttu-id="3a8e5-129">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="3a8e5-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
