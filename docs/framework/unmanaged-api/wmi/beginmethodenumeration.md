---
title: 开始方法枚举函数（非托管 API 引用）
description: BeginMethodEee）函数开始枚举对象的方法
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 876f5810fffab7fa98cd4d46715e13569ab95f6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175039"
---
# <a name="beginmethodenumeration-function"></a><span data-ttu-id="82be8-103">BeginMethodEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="82be8-103">BeginMethodEnumeration function</span></span>
<span data-ttu-id="82be8-104">开始枚举可用于对象的方法。</span><span class="sxs-lookup"><span data-stu-id="82be8-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="82be8-105">语法</span><span class="sxs-lookup"><span data-stu-id="82be8-105">Syntax</span></span>  
  
```cpp
HRESULT BeginMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="82be8-106">parameters</span><span class="sxs-lookup"><span data-stu-id="82be8-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="82be8-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="82be8-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="82be8-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="82be8-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="82be8-109">[在]所有方法的零 （0） 或指定枚举范围的标志。</span><span class="sxs-lookup"><span data-stu-id="82be8-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="82be8-110">以下标志在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="82be8-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="82be8-111">一直</span><span class="sxs-lookup"><span data-stu-id="82be8-111">Constant</span></span>  |<span data-ttu-id="82be8-112">值</span><span class="sxs-lookup"><span data-stu-id="82be8-112">Value</span></span>  |<span data-ttu-id="82be8-113">说明</span><span class="sxs-lookup"><span data-stu-id="82be8-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="82be8-114">0x10</span><span class="sxs-lookup"><span data-stu-id="82be8-114">0x10</span></span> | <span data-ttu-id="82be8-115">将枚举限制为在类本身中定义的方法。</span><span class="sxs-lookup"><span data-stu-id="82be8-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="82be8-116">0x20</span><span class="sxs-lookup"><span data-stu-id="82be8-116">0x20</span></span> | <span data-ttu-id="82be8-117">将枚举限制为从基类继承的属性。</span><span class="sxs-lookup"><span data-stu-id="82be8-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="82be8-118">返回值</span><span class="sxs-lookup"><span data-stu-id="82be8-118">Return value</span></span>

<span data-ttu-id="82be8-119">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="82be8-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="82be8-120">一直</span><span class="sxs-lookup"><span data-stu-id="82be8-120">Constant</span></span>  |<span data-ttu-id="82be8-121">值</span><span class="sxs-lookup"><span data-stu-id="82be8-121">Value</span></span>  |<span data-ttu-id="82be8-122">说明</span><span class="sxs-lookup"><span data-stu-id="82be8-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="82be8-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="82be8-123">0x80041008</span></span> | <span data-ttu-id="82be8-124">`lEnnumFlags`是非零，不是指定的标志之一。</span><span class="sxs-lookup"><span data-stu-id="82be8-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="82be8-125">0</span><span class="sxs-lookup"><span data-stu-id="82be8-125">0</span></span> | <span data-ttu-id="82be8-126">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="82be8-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="82be8-127">备注</span><span class="sxs-lookup"><span data-stu-id="82be8-127">Remarks</span></span>

<span data-ttu-id="82be8-128">此函数包装对[IWbemClassObject 的调用：：开始方法枚举](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration)方法。</span><span class="sxs-lookup"><span data-stu-id="82be8-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="82be8-129">仅当当前对象是类定义时，才支持此方法调用。</span><span class="sxs-lookup"><span data-stu-id="82be8-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="82be8-130">方法操作从指向实例的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指针中不可用。</span><span class="sxs-lookup"><span data-stu-id="82be8-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="82be8-131">对于[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的给定实例，方法的枚举顺序保证为不变。</span><span class="sxs-lookup"><span data-stu-id="82be8-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="82be8-132">要求</span><span class="sxs-lookup"><span data-stu-id="82be8-132">Requirements</span></span>  
 <span data-ttu-id="82be8-133">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82be8-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82be8-134">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="82be8-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="82be8-135">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="82be8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82be8-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82be8-136">See also</span></span>

- [<span data-ttu-id="82be8-137">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="82be8-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
