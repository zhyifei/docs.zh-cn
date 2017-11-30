---
title: "CreateInstanceEnumWmi 函数 （非托管 API 参考）"
description: "CreateInstanceEnumWmi 函数返回包含指定类的满足选择条件的实例的枚举。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateInstanceEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateInstanceEnumWmi
helpviewer_keywords: CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19a4102796da7a5692eb5b9b459a6a95ff7409f9
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="a6a75-103">CreateInstanceEnumWmi 函数</span><span class="sxs-lookup"><span data-stu-id="a6a75-103">CreateInstanceEnumWmi function</span></span>
<span data-ttu-id="a6a75-104">返回一个枚举器返回满足指定的选择条件指定类的实例。</span><span class="sxs-lookup"><span data-stu-id="a6a75-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a6a75-105">语法</span><span class="sxs-lookup"><span data-stu-id="a6a75-105">Syntax</span></span>  
  
```  
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a><span data-ttu-id="a6a75-106">参数</span><span class="sxs-lookup"><span data-stu-id="a6a75-106">Parameters</span></span>

`strFilter`    
<span data-ttu-id="a6a75-107">[in]为其实例所需的类的名称。</span><span class="sxs-lookup"><span data-stu-id="a6a75-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="a6a75-108">此参数不能为`null`。</span><span class="sxs-lookup"><span data-stu-id="a6a75-108">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="a6a75-109">[in]影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="a6a75-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="a6a75-110">在中定义以下值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="a6a75-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="a6a75-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="a6a75-111">Constant</span></span>  |<span data-ttu-id="a6a75-112">值</span><span class="sxs-lookup"><span data-stu-id="a6a75-112">Value</span></span>  |<span data-ttu-id="a6a75-113">描述</span><span class="sxs-lookup"><span data-stu-id="a6a75-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="a6a75-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="a6a75-114">0x20000</span></span> | <span data-ttu-id="a6a75-115">如果集，该函数检索当前连接的区域设置的本地化命名空间中存储的修正的限定符。</span><span class="sxs-lookup"><span data-stu-id="a6a75-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="a6a75-116">如果未设置，函数将检索存储在即时命名空间限定符。</span><span class="sxs-lookup"><span data-stu-id="a6a75-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="a6a75-117">0</span><span class="sxs-lookup"><span data-stu-id="a6a75-117">0</span></span> | <span data-ttu-id="a6a75-118">在枚举层次结构中包括此和所有子类。</span><span class="sxs-lookup"><span data-stu-id="a6a75-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="a6a75-119">1</span><span class="sxs-lookup"><span data-stu-id="a6a75-119">1</span></span> | <span data-ttu-id="a6a75-120">枚举包括的此类仅纯实例，并排除的子类，可提供此类中找不到属性的所有实例。</span><span class="sxs-lookup"><span data-stu-id="a6a75-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="a6a75-121">0x10</span><span class="sxs-lookup"><span data-stu-id="a6a75-121">0x10</span></span> | <span data-ttu-id="a6a75-122">标志会导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="a6a75-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="a6a75-123">0x20</span><span class="sxs-lookup"><span data-stu-id="a6a75-123">0x20</span></span> | <span data-ttu-id="a6a75-124">该函数返回的只进的枚举器。</span><span class="sxs-lookup"><span data-stu-id="a6a75-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="a6a75-125">通常，只进的枚举器速度更快和使用的内存少于传统枚举器，但它们不允许调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="a6a75-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="a6a75-126">0</span><span class="sxs-lookup"><span data-stu-id="a6a75-126">0</span></span> | <span data-ttu-id="a6a75-127">WMI 将保留指向 enumration 中的对象的指针，直到它们被释放为止。</span><span class="sxs-lookup"><span data-stu-id="a6a75-127">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="a6a75-128">建议的标志是`WBEM_FLAG_RETURN_IMMEDIATELY`和`WBEM_FLAG_FORWARD_ONLY`为了获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="a6a75-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="a6a75-129">[in]通常，此值是`null`。</span><span class="sxs-lookup"><span data-stu-id="a6a75-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="a6a75-130">否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可能使用的提供程序提供请求的实例的实例。</span><span class="sxs-lookup"><span data-stu-id="a6a75-130">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`  
<span data-ttu-id="a6a75-131">[out]接收枚举数的指针。</span><span class="sxs-lookup"><span data-stu-id="a6a75-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="a6a75-132">[in]授权级别中。</span><span class="sxs-lookup"><span data-stu-id="a6a75-132">[in] The authorization level.</span></span>

<span data-ttu-id="a6a75-133">`impLevel`[in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="a6a75-133">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="a6a75-134">[in]指向的指针[IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx)对象，表示当前的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a6a75-134">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="a6a75-135">[in]用户名。</span><span class="sxs-lookup"><span data-stu-id="a6a75-135">[in] The user name.</span></span> <span data-ttu-id="a6a75-136">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="a6a75-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="a6a75-137">[in]密码。</span><span class="sxs-lookup"><span data-stu-id="a6a75-137">[in] The password.</span></span> <span data-ttu-id="a6a75-138">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="a6a75-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="a6a75-139">[in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="a6a75-139">[in] The domain name of the user.</span></span> <span data-ttu-id="a6a75-140">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="a6a75-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="a6a75-141">返回值</span><span class="sxs-lookup"><span data-stu-id="a6a75-141">Return value</span></span>

<span data-ttu-id="a6a75-142">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="a6a75-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a6a75-143">返回的常量</span><span class="sxs-lookup"><span data-stu-id="a6a75-143">Constant</span></span>  |<span data-ttu-id="a6a75-144">值</span><span class="sxs-lookup"><span data-stu-id="a6a75-144">Value</span></span>  |<span data-ttu-id="a6a75-145">描述</span><span class="sxs-lookup"><span data-stu-id="a6a75-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="a6a75-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="a6a75-146">0x80041003</span></span> | <span data-ttu-id="a6a75-147">用户没有权限查看的指定类的实例。</span><span class="sxs-lookup"><span data-stu-id="a6a75-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="a6a75-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a6a75-148">0x80041001</span></span> | <span data-ttu-id="a6a75-149">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="a6a75-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="a6a75-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="a6a75-150">0x80041010</span></span> | <span data-ttu-id="a6a75-151">`strFilter` 不存在。</span><span class="sxs-lookup"><span data-stu-id="a6a75-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a6a75-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a6a75-152">0x80041008</span></span> | <span data-ttu-id="a6a75-153">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="a6a75-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a6a75-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a6a75-154">0x80041006</span></span> | <span data-ttu-id="a6a75-155">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="a6a75-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="a6a75-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="a6a75-156">0x80041033</span></span> | <span data-ttu-id="a6a75-157">WMI 时可能已停止和重新启动。</span><span class="sxs-lookup"><span data-stu-id="a6a75-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="a6a75-158">调用[ConnectServerWmi](connectserverwmi.md)试。</span><span class="sxs-lookup"><span data-stu-id="a6a75-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="a6a75-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="a6a75-159">0x80041015</span></span> | <span data-ttu-id="a6a75-160">之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。</span><span class="sxs-lookup"><span data-stu-id="a6a75-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a6a75-161">0</span><span class="sxs-lookup"><span data-stu-id="a6a75-161">0</span></span> | <span data-ttu-id="a6a75-162">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="a6a75-162">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a6a75-163">备注</span><span class="sxs-lookup"><span data-stu-id="a6a75-163">Remarks</span></span>

<span data-ttu-id="a6a75-164">此函数包装对的调用[iwbemservices:: Createclassenum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="a6a75-164">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="a6a75-165">请注意，返回的枚举数可以有零个元素。</span><span class="sxs-lookup"><span data-stu-id="a6a75-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="a6a75-166">如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="a6a75-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6a75-167">要求</span><span class="sxs-lookup"><span data-stu-id="a6a75-167">Requirements</span></span>  
 <span data-ttu-id="a6a75-168">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6a75-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6a75-169">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a6a75-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a6a75-170">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6a75-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a75-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6a75-171">See also</span></span>  
[<span data-ttu-id="a6a75-172">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="a6a75-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
