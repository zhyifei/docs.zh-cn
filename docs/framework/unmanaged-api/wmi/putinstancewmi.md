---
title: "PutInstanceWmi 函数 （非托管 API 参考）"
description: "PutInstanceWmi 函数创建或更新现有类的实例。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: PutInstanceWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: PutInstanceWmi
helpviewer_keywords: PutInstanceWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1996103eea87562226537f9aa90dc337c56313c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="54a31-103">PutInstanceWmi 函数</span><span class="sxs-lookup"><span data-stu-id="54a31-103">PutInstanceWmi function</span></span>
<span data-ttu-id="54a31-104">创建或更新现有类的实例。</span><span class="sxs-lookup"><span data-stu-id="54a31-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="54a31-105">实例将写入 WMI 存储库。</span><span class="sxs-lookup"><span data-stu-id="54a31-105">The instance is written to the WMI repository.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="54a31-106">语法</span><span class="sxs-lookup"><span data-stu-id="54a31-106">Syntax</span></span>  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="54a31-107">参数</span><span class="sxs-lookup"><span data-stu-id="54a31-107">Parameters</span></span>

`pInst`    
<span data-ttu-id="54a31-108">[in]指向要写入的实例的指针。</span><span class="sxs-lookup"><span data-stu-id="54a31-108">[in] A pointer to the instance to be writen.</span></span>

`lFlags`   
<span data-ttu-id="54a31-109">[in]影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="54a31-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="54a31-110">在中定义以下值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="54a31-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="54a31-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="54a31-111">Constant</span></span>  |<span data-ttu-id="54a31-112">“值”</span><span class="sxs-lookup"><span data-stu-id="54a31-112">Value</span></span>  |<span data-ttu-id="54a31-113">描述</span><span class="sxs-lookup"><span data-stu-id="54a31-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="54a31-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="54a31-114">0x20000</span></span> | <span data-ttu-id="54a31-115">如果设置，WMI 不存储任何限定符与**Amended**风格。</span><span class="sxs-lookup"><span data-stu-id="54a31-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> </br> <span data-ttu-id="54a31-116">如果不设置，则假定此对象未本地化，以及所有的限定符是 storedwith 此实例。</span><span class="sxs-lookup"><span data-stu-id="54a31-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="54a31-117">0</span><span class="sxs-lookup"><span data-stu-id="54a31-117">0</span></span> | <span data-ttu-id="54a31-118">如果不存在，或如果它已存在对其进行覆盖，请创建该实例。</span><span class="sxs-lookup"><span data-stu-id="54a31-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="54a31-119">1</span><span class="sxs-lookup"><span data-stu-id="54a31-119">1</span></span> | <span data-ttu-id="54a31-120">更新的实例。</span><span class="sxs-lookup"><span data-stu-id="54a31-120">Update the instance.</span></span> <span data-ttu-id="54a31-121">实例必须存在才能成功的调用。</span><span class="sxs-lookup"><span data-stu-id="54a31-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="54a31-122">2</span><span class="sxs-lookup"><span data-stu-id="54a31-122">2</span></span> | <span data-ttu-id="54a31-123">创建实例。</span><span class="sxs-lookup"><span data-stu-id="54a31-123">Create the instance.</span></span> <span data-ttu-id="54a31-124">如果该实例已经存在，则调用将失败。</span><span class="sxs-lookup"><span data-stu-id="54a31-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="54a31-125">0x10</span><span class="sxs-lookup"><span data-stu-id="54a31-125">0x10</span></span> | <span data-ttu-id="54a31-126">标志会导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="54a31-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`  
<span data-ttu-id="54a31-127">[in]通常，此值是`null`。</span><span class="sxs-lookup"><span data-stu-id="54a31-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="54a31-128">否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可用的提供程序提供请求的类的实例。</span><span class="sxs-lookup"><span data-stu-id="54a31-128">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="54a31-129">[out]如果`null`，未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="54a31-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="54a31-130">如果`lFlags`包含`WBEM_FLAG_RETURN_IMMEDIATELY`，该函数将立即返回与`WBEM_S_NO_ERROR`。</span><span class="sxs-lookup"><span data-stu-id="54a31-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="54a31-131">`ppCallResult`参数接收一个指针，到新[IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx)对象。</span><span class="sxs-lookup"><span data-stu-id="54a31-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="54a31-132">返回值</span><span class="sxs-lookup"><span data-stu-id="54a31-132">Return value</span></span>

<span data-ttu-id="54a31-133">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="54a31-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="54a31-134">返回的常量</span><span class="sxs-lookup"><span data-stu-id="54a31-134">Constant</span></span>  |<span data-ttu-id="54a31-135">“值”</span><span class="sxs-lookup"><span data-stu-id="54a31-135">Value</span></span>  |<span data-ttu-id="54a31-136">描述</span><span class="sxs-lookup"><span data-stu-id="54a31-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="54a31-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="54a31-137">0x80041003</span></span> | <span data-ttu-id="54a31-138">用户没有权限来更新指定类的实例。</span><span class="sxs-lookup"><span data-stu-id="54a31-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="54a31-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="54a31-139">0x80041001</span></span> | <span data-ttu-id="54a31-140">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="54a31-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="54a31-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="54a31-141">0x80041010</span></span> | <span data-ttu-id="54a31-142">支持此实例的类无效。</span><span class="sxs-lookup"><span data-stu-id="54a31-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="54a31-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="54a31-143">0x80041028</span></span> | <span data-ttu-id="54a31-144">`null`已为不能为属性指定`null`，例如标记**索引**或**空白**限定符。</span><span class="sxs-lookup"><span data-stu-id="54a31-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="54a31-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="54a31-145">0x8004100f</span></span> | <span data-ttu-id="54a31-146">指定的实例不是有效的。</span><span class="sxs-lookup"><span data-stu-id="54a31-146">The specified instance is not valid.</span></span> <span data-ttu-id="54a31-147">(例如，调用`PutInstanceWmi`与类返回该值。)</span><span class="sxs-lookup"><span data-stu-id="54a31-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="54a31-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="54a31-148">0x80041008</span></span> | <span data-ttu-id="54a31-149">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="54a31-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="54a31-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="54a31-150">0x80041019</span></span> | <span data-ttu-id="54a31-151">`WBEM_FLAG_CREATE_ONLY`指定了标记，但是该实例已经存在。</span><span class="sxs-lookup"><span data-stu-id="54a31-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="54a31-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="54a31-152">0x80041002</span></span> | <span data-ttu-id="54a31-153">`WBEM_FLAG_UPDATE_ONLY`中指定`lFlags`，但该实例不存在。</span><span class="sxs-lookup"><span data-stu-id="54a31-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="54a31-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="54a31-154">0x80041006</span></span> | <span data-ttu-id="54a31-155">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="54a31-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="54a31-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="54a31-156">0x80041033</span></span> | <span data-ttu-id="54a31-157">WMI 时可能已停止和重新启动。</span><span class="sxs-lookup"><span data-stu-id="54a31-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="54a31-158">调用[ConnectServerWmi](connectserverwmi.md)试。</span><span class="sxs-lookup"><span data-stu-id="54a31-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="54a31-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="54a31-159">0x80041015</span></span> | <span data-ttu-id="54a31-160">之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。</span><span class="sxs-lookup"><span data-stu-id="54a31-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="54a31-161">0</span><span class="sxs-lookup"><span data-stu-id="54a31-161">0</span></span> | <span data-ttu-id="54a31-162">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="54a31-162">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="54a31-163">备注</span><span class="sxs-lookup"><span data-stu-id="54a31-163">Remarks</span></span>

<span data-ttu-id="54a31-164">此函数包装对的调用[IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="54a31-164">This function wraps a call to the [IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="54a31-165">`PutInstanceWmi`函数支持创建实例和更新现有的类的实例。</span><span class="sxs-lookup"><span data-stu-id="54a31-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="54a31-166">具体取决于如何`pCtx`设置参数，系统将更新某些或所有实例的属性。</span><span class="sxs-lookup"><span data-stu-id="54a31-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span> 

<span data-ttu-id="54a31-167">当实例指向`pInst`所属的子类，Windows 管理调用负责子类派生的类的所有提供程序。</span><span class="sxs-lookup"><span data-stu-id="54a31-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="54a31-168">所有这些提供程序必须成功执行原始`PutInstanceWmi`请求才能成功。</span><span class="sxs-lookup"><span data-stu-id="54a31-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="54a31-169">首先调用层次结构中支持的最顶层类的提供程序。</span><span class="sxs-lookup"><span data-stu-id="54a31-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="54a31-170">调用顺序会继续进行的最顶层类的子类和继续从顶部到底部直到 Windows 管理达到拥有指向的实例的类的提供程序`pInst`。</span><span class="sxs-lookup"><span data-stu-id="54a31-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="54a31-171">Windows 管理不调用任何实例的子类别的提供程序。</span><span class="sxs-lookup"><span data-stu-id="54a31-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span> 

<span data-ttu-id="54a31-172">当应用程序必须更新实例属于类层次结构，`pInst`参数必须指向包含要修改的属性的实例。</span><span class="sxs-lookup"><span data-stu-id="54a31-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="54a31-173">也就是说，考虑所属的目标实例**ClassB**。</span><span class="sxs-lookup"><span data-stu-id="54a31-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="54a31-174">**ClassB**实例派生自**ClassA**，和**ClassA**定义该属性**PropA**。</span><span class="sxs-lookup"><span data-stu-id="54a31-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="54a31-175">如果应用程序想要对的值进行更改**PropA**中**ClassB**实例，它必须设置`pInst`到该实例，而不是实例**ClassA**.</span><span class="sxs-lookup"><span data-stu-id="54a31-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="54a31-176">调用`PutInstanceWmi`不允许抽象类的实例上。</span><span class="sxs-lookup"><span data-stu-id="54a31-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="54a31-177">如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="54a31-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="54a31-178">惠?</span><span class="sxs-lookup"><span data-stu-id="54a31-178">Requirements</span></span>  
 <span data-ttu-id="54a31-179">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54a31-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54a31-180">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="54a31-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="54a31-181">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="54a31-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54a31-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="54a31-182">See also</span></span>  
[<span data-ttu-id="54a31-183">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="54a31-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
