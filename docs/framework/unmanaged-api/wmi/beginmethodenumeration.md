---
title: BeginMethodEnumeration 函数（非托管 API 参考）
description: BeginMethodEnumeration 函数开始枚举对象的方法
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
ms.openlocfilehash: a27787052757098d4edb2d8516e22d8a03b7009a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138793"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="b53cb-103">BeginEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="b53cb-103">BeginEnumeration function</span></span>
<span data-ttu-id="b53cb-104">开始枚举可用于对象的方法。</span><span class="sxs-lookup"><span data-stu-id="b53cb-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b53cb-105">语法</span><span class="sxs-lookup"><span data-stu-id="b53cb-105">Syntax</span></span>  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="b53cb-106">参数</span><span class="sxs-lookup"><span data-stu-id="b53cb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b53cb-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="b53cb-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b53cb-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="b53cb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="b53cb-109">中对于所有方法为零（0）或指定枚举范围的标志。</span><span class="sxs-lookup"><span data-stu-id="b53cb-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="b53cb-110">以下标志是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="b53cb-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="b53cb-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="b53cb-111">Constant</span></span>  |<span data-ttu-id="b53cb-112">“值”</span><span class="sxs-lookup"><span data-stu-id="b53cb-112">Value</span></span>  |<span data-ttu-id="b53cb-113">描述</span><span class="sxs-lookup"><span data-stu-id="b53cb-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="b53cb-114">0x10</span><span class="sxs-lookup"><span data-stu-id="b53cb-114">0x10</span></span> | <span data-ttu-id="b53cb-115">将枚举限制为类本身中定义的方法。</span><span class="sxs-lookup"><span data-stu-id="b53cb-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="b53cb-116">0x20</span><span class="sxs-lookup"><span data-stu-id="b53cb-116">0x20</span></span> | <span data-ttu-id="b53cb-117">将枚举限制为从基类继承的属性。</span><span class="sxs-lookup"><span data-stu-id="b53cb-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="b53cb-118">返回值</span><span class="sxs-lookup"><span data-stu-id="b53cb-118">Return value</span></span>

<span data-ttu-id="b53cb-119">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="b53cb-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b53cb-120">返回的常量</span><span class="sxs-lookup"><span data-stu-id="b53cb-120">Constant</span></span>  |<span data-ttu-id="b53cb-121">“值”</span><span class="sxs-lookup"><span data-stu-id="b53cb-121">Value</span></span>  |<span data-ttu-id="b53cb-122">描述</span><span class="sxs-lookup"><span data-stu-id="b53cb-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b53cb-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b53cb-123">0x80041008</span></span> | <span data-ttu-id="b53cb-124">`lEnnumFlags` 为非零值，并且不是指定标志之一。</span><span class="sxs-lookup"><span data-stu-id="b53cb-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b53cb-125">0</span><span class="sxs-lookup"><span data-stu-id="b53cb-125">0</span></span> | <span data-ttu-id="b53cb-126">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="b53cb-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b53cb-127">备注</span><span class="sxs-lookup"><span data-stu-id="b53cb-127">Remarks</span></span>

<span data-ttu-id="b53cb-128">此函数包装对[IWbemClassObject：： BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="b53cb-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="b53cb-129">仅当当前对象为类定义时，才支持此方法调用。</span><span class="sxs-lookup"><span data-stu-id="b53cb-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="b53cb-130">指向实例的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指针不提供方法操作。</span><span class="sxs-lookup"><span data-stu-id="b53cb-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="b53cb-131">对于给定的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例，可保证方法的枚举顺序是固定的。</span><span class="sxs-lookup"><span data-stu-id="b53cb-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="b53cb-132">要求</span><span class="sxs-lookup"><span data-stu-id="b53cb-132">Requirements</span></span>  
 <span data-ttu-id="b53cb-133">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b53cb-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b53cb-134">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="b53cb-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b53cb-135">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b53cb-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b53cb-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="b53cb-136">See also</span></span>

- [<span data-ttu-id="b53cb-137">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="b53cb-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
