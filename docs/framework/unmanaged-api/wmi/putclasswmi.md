---
title: "PutClassWmi 函数 （非托管 API 参考）"
description: "PutClassWmi 函数创建一个新类，或更新现有。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 219cec2096cd3d1dfe1e0d3c0903b62692e444e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="putclasswmi-function"></a><span data-ttu-id="32cf0-103">PutClassWmi 函数</span><span class="sxs-lookup"><span data-stu-id="32cf0-103">PutClassWmi function</span></span>
<span data-ttu-id="32cf0-104">创建新的类或更新现有。</span><span class="sxs-lookup"><span data-stu-id="32cf0-104">Creates a new class or updates an existing one.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="32cf0-105">语法</span><span class="sxs-lookup"><span data-stu-id="32cf0-105">Syntax</span></span>  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="32cf0-106">参数</span><span class="sxs-lookup"><span data-stu-id="32cf0-106">Parameters</span></span>

`pObject`    
<span data-ttu-id="32cf0-107">[in]指向有效的类定义的指针。</span><span class="sxs-lookup"><span data-stu-id="32cf0-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="32cf0-108">它必须使用所有必需的属性值正确初始化。</span><span class="sxs-lookup"><span data-stu-id="32cf0-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`   
<span data-ttu-id="32cf0-109">[in]影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="32cf0-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="32cf0-110">在中定义以下值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="32cf0-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="32cf0-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="32cf0-111">Constant</span></span>  |<span data-ttu-id="32cf0-112">“值”</span><span class="sxs-lookup"><span data-stu-id="32cf0-112">Value</span></span>  |<span data-ttu-id="32cf0-113">描述</span><span class="sxs-lookup"><span data-stu-id="32cf0-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="32cf0-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="32cf0-114">0x20000</span></span> | <span data-ttu-id="32cf0-115">如果集，WMI 不存储任何限定符与已修正的风格。</span><span class="sxs-lookup"><span data-stu-id="32cf0-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> </br> <span data-ttu-id="32cf0-116">如果不设置，则假定此对象未本地化，以及所有的限定符是 storedwith 此实例。</span><span class="sxs-lookup"><span data-stu-id="32cf0-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="32cf0-117">0</span><span class="sxs-lookup"><span data-stu-id="32cf0-117">0</span></span> | <span data-ttu-id="32cf0-118">如果不存在，或如果它已存在对其进行覆盖，请创建类。</span><span class="sxs-lookup"><span data-stu-id="32cf0-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="32cf0-119">1</span><span class="sxs-lookup"><span data-stu-id="32cf0-119">1</span></span> | <span data-ttu-id="32cf0-120">更新类。</span><span class="sxs-lookup"><span data-stu-id="32cf0-120">Update the class.</span></span> <span data-ttu-id="32cf0-121">类必须存在才能成功的调用。</span><span class="sxs-lookup"><span data-stu-id="32cf0-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="32cf0-122">2</span><span class="sxs-lookup"><span data-stu-id="32cf0-122">2</span></span> | <span data-ttu-id="32cf0-123">创建类。</span><span class="sxs-lookup"><span data-stu-id="32cf0-123">Create the class.</span></span> <span data-ttu-id="32cf0-124">如果该类已存在，则调用将失败。</span><span class="sxs-lookup"><span data-stu-id="32cf0-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="32cf0-125">0x10</span><span class="sxs-lookup"><span data-stu-id="32cf0-125">0x10</span></span> | <span data-ttu-id="32cf0-126">标志会导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="32cf0-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="32cf0-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="32cf0-127">0x10000</span></span> | <span data-ttu-id="32cf0-128">在调用时，请求提供程序必须指定此标志`PutClassWmi`以指示此类已更改。</span><span class="sxs-lookup"><span data-stu-id="32cf0-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="32cf0-129">0</span><span class="sxs-lookup"><span data-stu-id="32cf0-129">0</span></span> | <span data-ttu-id="32cf0-130">允许的类，如果有任何派生的类和类的任何实例更新。</span><span class="sxs-lookup"><span data-stu-id="32cf0-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="32cf0-131">同时它还允许出了如果更改只需为重要的限定符，如描述限定符，在所有情况下的更新。</span><span class="sxs-lookup"><span data-stu-id="32cf0-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="32cf0-132">如果类具有实例或更改是对重要限定符，则更新失败。</span><span class="sxs-lookup"><span data-stu-id="32cf0-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="32cf0-133">0x20</span><span class="sxs-lookup"><span data-stu-id="32cf0-133">0x20</span></span> | <span data-ttu-id="32cf0-134">允许的类的更新，即使有子类别，只要更改不会使用子类的任何冲突。</span><span class="sxs-lookup"><span data-stu-id="32cf0-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="32cf0-135">例如，此标志将允许新属性添加到中的任何子类未以前提到的基类。</span><span class="sxs-lookup"><span data-stu-id="32cf0-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="32cf0-136">如果类具有实例，则更新失败。</span><span class="sxs-lookup"><span data-stu-id="32cf0-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="32cf0-137">0x40</span><span class="sxs-lookup"><span data-stu-id="32cf0-137">0x40</span></span> | <span data-ttu-id="32cf0-138">时存在冲突的子类别，强制实施的类的更新。</span><span class="sxs-lookup"><span data-stu-id="32cf0-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="32cf0-139">例如，如果类限定符定义在子类中，并且基类尝试将同一限定符与一个现有的数值冲突添加此标志将强制更新。</span><span class="sxs-lookup"><span data-stu-id="32cf0-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with thte existing one.</span></span> <span data-ttu-id="32cf0-140">在强制模式下，通过删除子类别中发生冲突的限定符，可解决 tis 冲突。</span><span class="sxs-lookup"><span data-stu-id="32cf0-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`  
<span data-ttu-id="32cf0-141">[in]通常，此值是`null`。</span><span class="sxs-lookup"><span data-stu-id="32cf0-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="32cf0-142">否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可用的提供程序提供请求的类的实例。</span><span class="sxs-lookup"><span data-stu-id="32cf0-142">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="32cf0-143">[out]如果`null`，未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="32cf0-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="32cf0-144">如果`lFlags`包含`WBEM_FLAG_RETURN_IMMEDIATELY`，该函数将立即返回与`WBEM_S_NO_ERROR`。</span><span class="sxs-lookup"><span data-stu-id="32cf0-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="32cf0-145">`ppCallResult`参数接收一个指针，到新[IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx)对象。</span><span class="sxs-lookup"><span data-stu-id="32cf0-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="32cf0-146">返回值</span><span class="sxs-lookup"><span data-stu-id="32cf0-146">Return value</span></span>

<span data-ttu-id="32cf0-147">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="32cf0-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="32cf0-148">返回的常量</span><span class="sxs-lookup"><span data-stu-id="32cf0-148">Constant</span></span>  |<span data-ttu-id="32cf0-149">“值”</span><span class="sxs-lookup"><span data-stu-id="32cf0-149">Value</span></span>  |<span data-ttu-id="32cf0-150">描述</span><span class="sxs-lookup"><span data-stu-id="32cf0-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="32cf0-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="32cf0-151">0x80041003</span></span> | <span data-ttu-id="32cf0-152">用户没有创建或修改类的权限。</span><span class="sxs-lookup"><span data-stu-id="32cf0-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="32cf0-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="32cf0-153">0x80041001</span></span> | <span data-ttu-id="32cf0-154">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="32cf0-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="32cf0-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="32cf0-155">0x80041010</span></span> | <span data-ttu-id="32cf0-156">指定的类不是有效的。</span><span class="sxs-lookup"><span data-stu-id="32cf0-156">The specified class is not valid.</span></span> <span data-ttu-id="32cf0-157">通常情况下，这指示`pObject`指定的实例对象。</span><span class="sxs-lookup"><span data-stu-id="32cf0-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="32cf0-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="32cf0-158">0x80041008</span></span> | <span data-ttu-id="32cf0-159">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="32cf0-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="32cf0-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="32cf0-160">0x80041016</span></span> | <span data-ttu-id="32cf0-161">指定的类名称无效。</span><span class="sxs-lookup"><span data-stu-id="32cf0-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="32cf0-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="32cf0-162">0x80041025</span></span> | <span data-ttu-id="32cf0-163">尝试进行的更改会使子类无效。</span><span class="sxs-lookup"><span data-stu-id="32cf0-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="32cf0-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="32cf0-164">0x80041019</span></span> | <span data-ttu-id="32cf0-165">`WBEM_FLAG_CREATE_ONLY`指定了标记，但该类已存在。</span><span class="sxs-lookup"><span data-stu-id="32cf0-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="32cf0-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="32cf0-166">0x80041002</span></span> | <span data-ttu-id="32cf0-167">`WBEM_FLAG_UPDATE_ONLY`中指定`lFlags`，但找不到类。</span><span class="sxs-lookup"><span data-stu-id="32cf0-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="32cf0-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="32cf0-168">0x80041020</span></span> | <span data-ttu-id="32cf0-169">类的必需的属性不是所有尚未设置。</span><span class="sxs-lookup"><span data-stu-id="32cf0-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="32cf0-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="32cf0-170">0x80041006</span></span> | <span data-ttu-id="32cf0-171">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="32cf0-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="32cf0-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="32cf0-172">0x80041033</span></span> | <span data-ttu-id="32cf0-173">WMI 时可能已停止和重新启动。</span><span class="sxs-lookup"><span data-stu-id="32cf0-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="32cf0-174">调用[ConnectServerWmi](connectserverwmi.md)试。</span><span class="sxs-lookup"><span data-stu-id="32cf0-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="32cf0-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="32cf0-175">0x80041015</span></span> | <span data-ttu-id="32cf0-176">之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。</span><span class="sxs-lookup"><span data-stu-id="32cf0-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="32cf0-177">0</span><span class="sxs-lookup"><span data-stu-id="32cf0-177">0</span></span> | <span data-ttu-id="32cf0-178">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="32cf0-178">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="32cf0-179">备注</span><span class="sxs-lookup"><span data-stu-id="32cf0-179">Remarks</span></span>

<span data-ttu-id="32cf0-180">此函数包装对的调用[IWbemServices::PutClass](https://msdn.microsoft.com/library/aa392113(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="32cf0-180">This function wraps a call to the [IWbemServices::PutClass](https://msdn.microsoft.com/library/aa392113(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="32cf0-181">用户可能不具有名称的开头或结尾下划线 chacater 创建的类</span><span class="sxs-lookup"><span data-stu-id="32cf0-181">The user may not create classes with names that begin or end with an underscore chacater</span></span>

<span data-ttu-id="32cf0-182">如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="32cf0-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="32cf0-183">惠?</span><span class="sxs-lookup"><span data-stu-id="32cf0-183">Requirements</span></span>  
 <span data-ttu-id="32cf0-184">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="32cf0-184">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32cf0-185">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="32cf0-185">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="32cf0-186">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="32cf0-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32cf0-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="32cf0-187">See also</span></span>  
[<span data-ttu-id="32cf0-188">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="32cf0-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
