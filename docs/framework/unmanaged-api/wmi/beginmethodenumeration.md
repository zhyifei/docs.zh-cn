---
title: BeginMethodEnumeration 函数 （非托管 API 参考）
description: BeginMethodEnumeration 函数开始枚举的对象的方法
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e69625184aca7d1ebd4bb0b7dc7c4958596b906a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000338"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="15a97-103">BeginEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="15a97-103">BeginEnumeration function</span></span>
<span data-ttu-id="15a97-104">开始为对象提供的方法的枚举。</span><span class="sxs-lookup"><span data-stu-id="15a97-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="15a97-105">语法</span><span class="sxs-lookup"><span data-stu-id="15a97-105">Syntax</span></span>  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="15a97-106">参数</span><span class="sxs-lookup"><span data-stu-id="15a97-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="15a97-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="15a97-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="15a97-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="15a97-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="15a97-109">[in]零 (0) 的所有方法，或指定范围的枚举的标志。</span><span class="sxs-lookup"><span data-stu-id="15a97-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="15a97-110">在中定义的以下标志*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="15a97-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="15a97-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="15a97-111">Constant</span></span>  |<span data-ttu-id="15a97-112">“值”</span><span class="sxs-lookup"><span data-stu-id="15a97-112">Value</span></span>  |<span data-ttu-id="15a97-113">描述</span><span class="sxs-lookup"><span data-stu-id="15a97-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="15a97-114">0x10</span><span class="sxs-lookup"><span data-stu-id="15a97-114">0x10</span></span> | <span data-ttu-id="15a97-115">限制对自身的类中定义的方法的枚举。</span><span class="sxs-lookup"><span data-stu-id="15a97-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="15a97-116">0x20</span><span class="sxs-lookup"><span data-stu-id="15a97-116">0x20</span></span> | <span data-ttu-id="15a97-117">限制对从基类继承的属性的枚举。</span><span class="sxs-lookup"><span data-stu-id="15a97-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="15a97-118">返回值</span><span class="sxs-lookup"><span data-stu-id="15a97-118">Return value</span></span>

<span data-ttu-id="15a97-119">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="15a97-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="15a97-120">返回的常量</span><span class="sxs-lookup"><span data-stu-id="15a97-120">Constant</span></span>  |<span data-ttu-id="15a97-121">“值”</span><span class="sxs-lookup"><span data-stu-id="15a97-121">Value</span></span>  |<span data-ttu-id="15a97-122">描述</span><span class="sxs-lookup"><span data-stu-id="15a97-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="15a97-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="15a97-123">0x80041008</span></span> | <span data-ttu-id="15a97-124">`lEnnumFlags` 为非零值并不是指定的标志之一。</span><span class="sxs-lookup"><span data-stu-id="15a97-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="15a97-125">0</span><span class="sxs-lookup"><span data-stu-id="15a97-125">0</span></span> | <span data-ttu-id="15a97-126">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="15a97-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="15a97-127">备注</span><span class="sxs-lookup"><span data-stu-id="15a97-127">Remarks</span></span>

<span data-ttu-id="15a97-128">此函数包装对的调用[IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration)方法。</span><span class="sxs-lookup"><span data-stu-id="15a97-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="15a97-129">如果当前对象是类定义，则仅支持此方法调用。</span><span class="sxs-lookup"><span data-stu-id="15a97-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="15a97-130">方法操作不能从[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向实例的指针。</span><span class="sxs-lookup"><span data-stu-id="15a97-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="15a97-131">保证在其中枚举了方法的顺序是固定的给定实例的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)。</span><span class="sxs-lookup"><span data-stu-id="15a97-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="15a97-132">要求</span><span class="sxs-lookup"><span data-stu-id="15a97-132">Requirements</span></span>  
 <span data-ttu-id="15a97-133">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15a97-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a97-134">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="15a97-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="15a97-135">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="15a97-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a97-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="15a97-136">See also</span></span>  
[<span data-ttu-id="15a97-137">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="15a97-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
