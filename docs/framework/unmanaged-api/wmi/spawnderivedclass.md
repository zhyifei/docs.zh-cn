---
title: "SpawnDerivedClass 函数 （非托管 API 参考）"
description: "SpawnDerivedClass 函数将创建一个派生自对象的新对象。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnDerivedClass
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnDerivedClass
helpviewer_keywords: SpawnDerivedClass function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51a0dd0013b1bb3898bcc81ee2d64be20a5b6ecc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="2be01-103">SpawnDerivedClass 函数</span><span class="sxs-lookup"><span data-stu-id="2be01-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="2be01-104">从指定的对象创建新派生的类对象。</span><span class="sxs-lookup"><span data-stu-id="2be01-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2be01-105">语法</span><span class="sxs-lookup"><span data-stu-id="2be01-105">Syntax</span></span>  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="2be01-106">参数</span><span class="sxs-lookup"><span data-stu-id="2be01-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2be01-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="2be01-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2be01-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="2be01-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="2be01-109">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="2be01-109">[in] Reserved.</span></span> <span data-ttu-id="2be01-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="2be01-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="2be01-111">[out]接收到新的类定义对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2be01-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="2be01-112">如果发生错误，新的对象不是返回，和`ppNewClass`左未修改形式。</span><span class="sxs-lookup"><span data-stu-id="2be01-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="2be01-113">其值不能为`null`。</span><span class="sxs-lookup"><span data-stu-id="2be01-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="2be01-114">返回值</span><span class="sxs-lookup"><span data-stu-id="2be01-114">Return value</span></span>

<span data-ttu-id="2be01-115">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="2be01-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2be01-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="2be01-116">Constant</span></span>  |<span data-ttu-id="2be01-117">“值”</span><span class="sxs-lookup"><span data-stu-id="2be01-117">Value</span></span>  |<span data-ttu-id="2be01-118">描述</span><span class="sxs-lookup"><span data-stu-id="2be01-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="2be01-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="2be01-119">0x80041001</span></span> | <span data-ttu-id="2be01-120">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="2be01-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="2be01-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="2be01-121">0x80041016</span></span> | <span data-ttu-id="2be01-122">已请求了无效的操作，例如从实例中，生成一个类。</span><span class="sxs-lookup"><span data-stu-id="2be01-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="2be01-123">源类是未完全定义的或注册 Windows 管理中，因此不允许新的派生的类。</span><span class="sxs-lookup"><span data-stu-id="2be01-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2be01-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="2be01-124">0x80041006</span></span> | <span data-ttu-id="2be01-125">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="2be01-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2be01-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="2be01-126">0x80041008</span></span> | <span data-ttu-id="2be01-127">`ppNewClass` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="2be01-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="2be01-128">0</span><span class="sxs-lookup"><span data-stu-id="2be01-128">0</span></span> | <span data-ttu-id="2be01-129">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="2be01-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2be01-130">备注</span><span class="sxs-lookup"><span data-stu-id="2be01-130">Remarks</span></span>

<span data-ttu-id="2be01-131">此函数包装对的调用[IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="2be01-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="2be01-132">`ptr`必须是对象的一个将成为生成的父类的类定义。</span><span class="sxs-lookup"><span data-stu-id="2be01-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="2be01-133">返回的对象将成为当前对象的一个子类。</span><span class="sxs-lookup"><span data-stu-id="2be01-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="2be01-134">新的对象中返回`ppNewClass`自动成为当前对象的一个子类。</span><span class="sxs-lookup"><span data-stu-id="2be01-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="2be01-135">不能重写此行为。</span><span class="sxs-lookup"><span data-stu-id="2be01-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="2be01-136">不没有可以用来创建子类 （派生类） 的任何其他方法。</span><span class="sxs-lookup"><span data-stu-id="2be01-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="2be01-137">惠?</span><span class="sxs-lookup"><span data-stu-id="2be01-137">Requirements</span></span>  
 <span data-ttu-id="2be01-138">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2be01-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2be01-139">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2be01-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2be01-140">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2be01-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be01-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="2be01-141">See also</span></span>  
[<span data-ttu-id="2be01-142">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="2be01-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
