---
title: "SpawnInstance 函数 （非托管 API 参考）"
description: "SpawnInstance 函数将创建一个类的新实例。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnInstance
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnInstance
helpviewer_keywords: SpawnInstance function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 68508f3000e7f4ac481f940ef4c715366c37125c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="spawninstance-function"></a><span data-ttu-id="fcaed-103">SpawnInstance 函数</span><span class="sxs-lookup"><span data-stu-id="fcaed-103">SpawnInstance function</span></span>
<span data-ttu-id="fcaed-104">创建一个类的新实例。</span><span class="sxs-lookup"><span data-stu-id="fcaed-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fcaed-105">语法</span><span class="sxs-lookup"><span data-stu-id="fcaed-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="fcaed-106">参数</span><span class="sxs-lookup"><span data-stu-id="fcaed-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fcaed-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="fcaed-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="fcaed-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="fcaed-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="fcaed-109">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="fcaed-109">[in] Reserved.</span></span> <span data-ttu-id="fcaed-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="fcaed-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="fcaed-111">[out]接收到类的新实例的指针。</span><span class="sxs-lookup"><span data-stu-id="fcaed-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="fcaed-112">如果发生错误，新的对象不是返回，和`ppNewInstance`左未修改形式。</span><span class="sxs-lookup"><span data-stu-id="fcaed-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="fcaed-113">返回值</span><span class="sxs-lookup"><span data-stu-id="fcaed-113">Return value</span></span>

<span data-ttu-id="fcaed-114">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="fcaed-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fcaed-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="fcaed-115">Constant</span></span>  |<span data-ttu-id="fcaed-116">“值”</span><span class="sxs-lookup"><span data-stu-id="fcaed-116">Value</span></span>  |<span data-ttu-id="fcaed-117">描述</span><span class="sxs-lookup"><span data-stu-id="fcaed-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="fcaed-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="fcaed-118">0x80041020</span></span> | <span data-ttu-id="fcaed-119">`ptr`不是有效的类定义，无法生成新实例。</span><span class="sxs-lookup"><span data-stu-id="fcaed-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="fcaed-120">不完整，或者它具有不已注册到 Windows 管理中调用[PutClassWmi](putclasswmi.md)。</span><span class="sxs-lookup"><span data-stu-id="fcaed-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fcaed-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fcaed-121">0x80041006</span></span> | <span data-ttu-id="fcaed-122">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="fcaed-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fcaed-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fcaed-123">0x80041008</span></span> | <span data-ttu-id="fcaed-124">`ppNewClass` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="fcaed-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="fcaed-125">0</span><span class="sxs-lookup"><span data-stu-id="fcaed-125">0</span></span> | <span data-ttu-id="fcaed-126">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="fcaed-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fcaed-127">备注</span><span class="sxs-lookup"><span data-stu-id="fcaed-127">Remarks</span></span>

<span data-ttu-id="fcaed-128">此函数包装对的调用[IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="fcaed-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="fcaed-129">`ptr`必须是类定义从获取 Windows 管理。</span><span class="sxs-lookup"><span data-stu-id="fcaed-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="fcaed-130">（请注意，支持生成实例中的实例，但返回的实例为空。）然后可以使用此类定义来创建新实例。</span><span class="sxs-lookup"><span data-stu-id="fcaed-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="fcaed-131">调用[PutInstanceWmi](putinstancewmi.md)函数是必需的如果你想要将该实例写入到 Windows 管理。</span><span class="sxs-lookup"><span data-stu-id="fcaed-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>




<span data-ttu-id="fcaed-132">新的对象中返回`ppNewClass`自动成为当前对象的一个子类。</span><span class="sxs-lookup"><span data-stu-id="fcaed-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="fcaed-133">不能重写此行为。</span><span class="sxs-lookup"><span data-stu-id="fcaed-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="fcaed-134">不没有可以用来创建子类 （派生类） 的任何其他方法。</span><span class="sxs-lookup"><span data-stu-id="fcaed-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="fcaed-135">惠?</span><span class="sxs-lookup"><span data-stu-id="fcaed-135">Requirements</span></span>  
 <span data-ttu-id="fcaed-136">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fcaed-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcaed-137">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fcaed-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fcaed-138">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fcaed-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcaed-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcaed-139">See also</span></span>  
[<span data-ttu-id="fcaed-140">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="fcaed-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
