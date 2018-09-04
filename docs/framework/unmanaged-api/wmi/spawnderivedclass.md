---
title: SpawnDerivedClass 函数 （非托管 API 参考）
description: SpawnDerivedClass 函数创建新的对象从对象派生的。
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04df65a29584f7e2de44389d815b915a541e38f0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507492"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="bea7f-103">SpawnDerivedClass 函数</span><span class="sxs-lookup"><span data-stu-id="bea7f-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="bea7f-104">从指定对象创建新派生的类对象。</span><span class="sxs-lookup"><span data-stu-id="bea7f-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bea7f-105">语法</span><span class="sxs-lookup"><span data-stu-id="bea7f-105">Syntax</span></span>  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="bea7f-106">参数</span><span class="sxs-lookup"><span data-stu-id="bea7f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="bea7f-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="bea7f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="bea7f-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="bea7f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="bea7f-109">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="bea7f-109">[in] Reserved.</span></span> <span data-ttu-id="bea7f-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="bea7f-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="bea7f-111">[out]接收指向新的类定义对象的指针。</span><span class="sxs-lookup"><span data-stu-id="bea7f-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="bea7f-112">如果发生错误，新对象不是返回，和`ppNewClass`左侧不被修改。</span><span class="sxs-lookup"><span data-stu-id="bea7f-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="bea7f-113">其值不能为`null`。</span><span class="sxs-lookup"><span data-stu-id="bea7f-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="bea7f-114">返回值</span><span class="sxs-lookup"><span data-stu-id="bea7f-114">Return value</span></span>

<span data-ttu-id="bea7f-115">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="bea7f-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bea7f-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="bea7f-116">Constant</span></span>  |<span data-ttu-id="bea7f-117">“值”</span><span class="sxs-lookup"><span data-stu-id="bea7f-117">Value</span></span>  |<span data-ttu-id="bea7f-118">描述</span><span class="sxs-lookup"><span data-stu-id="bea7f-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="bea7f-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="bea7f-119">0x80041001</span></span> | <span data-ttu-id="bea7f-120">已存在时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="bea7f-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="bea7f-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="bea7f-121">0x80041016</span></span> | <span data-ttu-id="bea7f-122">请求了一个无效的操作，如生成的类的实例。</span><span class="sxs-lookup"><span data-stu-id="bea7f-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="bea7f-123">源类不是完全定义或注册到 Windows 管理，因此不允许新的派生的类。</span><span class="sxs-lookup"><span data-stu-id="bea7f-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bea7f-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bea7f-124">0x80041006</span></span> | <span data-ttu-id="bea7f-125">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="bea7f-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bea7f-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bea7f-126">0x80041008</span></span> | <span data-ttu-id="bea7f-127">`ppNewClass` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="bea7f-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="bea7f-128">0</span><span class="sxs-lookup"><span data-stu-id="bea7f-128">0</span></span> | <span data-ttu-id="bea7f-129">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="bea7f-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bea7f-130">备注</span><span class="sxs-lookup"><span data-stu-id="bea7f-130">Remarks</span></span>

<span data-ttu-id="bea7f-131">此函数包装对的调用[IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)方法。</span><span class="sxs-lookup"><span data-stu-id="bea7f-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="bea7f-132">`ptr` 必须将成为生成的对象的父类的类定义。</span><span class="sxs-lookup"><span data-stu-id="bea7f-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="bea7f-133">返回的对象将成为当前对象的子类。</span><span class="sxs-lookup"><span data-stu-id="bea7f-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="bea7f-134">新的对象中返回`ppNewClass`自动成为当前对象的子类。</span><span class="sxs-lookup"><span data-stu-id="bea7f-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="bea7f-135">不能重写此行为。</span><span class="sxs-lookup"><span data-stu-id="bea7f-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="bea7f-136">没有其他方法可以创建子类 （的派生类）。</span><span class="sxs-lookup"><span data-stu-id="bea7f-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="bea7f-137">要求</span><span class="sxs-lookup"><span data-stu-id="bea7f-137">Requirements</span></span>  
 <span data-ttu-id="bea7f-138">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bea7f-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bea7f-139">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bea7f-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bea7f-140">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bea7f-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea7f-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="bea7f-141">See also</span></span>  
[<span data-ttu-id="bea7f-142">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="bea7f-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
