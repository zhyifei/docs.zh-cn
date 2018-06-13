---
title: InheritsFrom 函数 （非托管 API 参考）
description: InheritsFrom 函数将确定类或实例派生自特定的父类。
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
ms.openlocfilehash: 87a1c1ee44d3b192747bd785f538c0332300ff50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461410"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="d27a1-103">InheritsFrom 函数</span><span class="sxs-lookup"><span data-stu-id="d27a1-103">InheritsFrom function</span></span>
<span data-ttu-id="d27a1-104">确定当前类或实例派生自指定的父类别。</span><span class="sxs-lookup"><span data-stu-id="d27a1-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d27a1-105">语法</span><span class="sxs-lookup"><span data-stu-id="d27a1-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="d27a1-106">参数</span><span class="sxs-lookup"><span data-stu-id="d27a1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d27a1-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="d27a1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d27a1-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="d27a1-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="d27a1-109">[in]类的名称。</span><span class="sxs-lookup"><span data-stu-id="d27a1-109">[in] The name of the class.</span></span> <span data-ttu-id="d27a1-110">`wszAncestor` 必须指向有效`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="d27a1-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="d27a1-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d27a1-111">Return value</span></span>

<span data-ttu-id="d27a1-112">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="d27a1-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d27a1-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="d27a1-113">Constant</span></span>  |<span data-ttu-id="d27a1-114">值</span><span class="sxs-lookup"><span data-stu-id="d27a1-114">Value</span></span>  |<span data-ttu-id="d27a1-115">描述</span><span class="sxs-lookup"><span data-stu-id="d27a1-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="d27a1-116">0</span><span class="sxs-lookup"><span data-stu-id="d27a1-116">0</span></span> | <span data-ttu-id="d27a1-117">当前对象继承自`wszAncestor`。</span><span class="sxs-lookup"><span data-stu-id="d27a1-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="d27a1-118">1</span><span class="sxs-lookup"><span data-stu-id="d27a1-118">1</span></span> | <span data-ttu-id="d27a1-119">当前对象不是继承自`wszAncestor`。</span><span class="sxs-lookup"><span data-stu-id="d27a1-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d27a1-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d27a1-120">0x80041008</span></span> | <span data-ttu-id="d27a1-121">`wszAncestor` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="d27a1-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="d27a1-122">备注</span><span class="sxs-lookup"><span data-stu-id="d27a1-122">Remarks</span></span>

<span data-ttu-id="d27a1-123">此函数包装对的调用[IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="d27a1-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d27a1-124">要求</span><span class="sxs-lookup"><span data-stu-id="d27a1-124">Requirements</span></span>  
 <span data-ttu-id="d27a1-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d27a1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d27a1-126">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d27a1-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d27a1-127">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d27a1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27a1-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d27a1-128">See also</span></span>  
[<span data-ttu-id="d27a1-129">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="d27a1-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
