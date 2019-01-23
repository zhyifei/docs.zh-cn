---
title: CreateInstanceEnumWmi 函数 （非托管 API 参考）
description: CreateInstanceEnumWmi 函数将返回包含满足选择条件指定类的实例的枚举器。
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba59d9d47d5c120eb2ff0a3a3c65e0fe8cdf75e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498289"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="c1f9d-103">CreateInstanceEnumWmi 函数</span><span class="sxs-lookup"><span data-stu-id="c1f9d-103">CreateInstanceEnumWmi function</span></span>
<span data-ttu-id="c1f9d-104">返回将返回满足指定的选择条件指定类的实例的枚举器。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c1f9d-105">语法</span><span class="sxs-lookup"><span data-stu-id="c1f9d-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="c1f9d-106">参数</span><span class="sxs-lookup"><span data-stu-id="c1f9d-106">Parameters</span></span>

`strFilter`    
<span data-ttu-id="c1f9d-107">[in]为其实例所需的类的名称。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="c1f9d-108">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-108">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="c1f9d-109">[in]影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="c1f9d-110">以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="c1f9d-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="c1f9d-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="c1f9d-111">Constant</span></span>  |<span data-ttu-id="c1f9d-112">“值”</span><span class="sxs-lookup"><span data-stu-id="c1f9d-112">Value</span></span>  |<span data-ttu-id="c1f9d-113">描述</span><span class="sxs-lookup"><span data-stu-id="c1f9d-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="c1f9d-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="c1f9d-114">0x20000</span></span> | <span data-ttu-id="c1f9d-115">如果集，该函数检索当前连接的区域设置的本地化命名空间中存储已修正的限定符。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="c1f9d-116">如果未设置，此函数检索仅立即命名空间中存储的限定符。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="c1f9d-117">0</span><span class="sxs-lookup"><span data-stu-id="c1f9d-117">0</span></span> | <span data-ttu-id="c1f9d-118">枚举在层次结构中包括此和所有子类。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="c1f9d-119">1</span><span class="sxs-lookup"><span data-stu-id="c1f9d-119">1</span></span> | <span data-ttu-id="c1f9d-120">枚举包括此类的仅纯实例，但不包括的子类提供此类中找不到属性的所有实例。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="c1f9d-121">0x10</span><span class="sxs-lookup"><span data-stu-id="c1f9d-121">0x10</span></span> | <span data-ttu-id="c1f9d-122">该标志会导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="c1f9d-123">0x20</span><span class="sxs-lookup"><span data-stu-id="c1f9d-123">0x20</span></span> | <span data-ttu-id="c1f9d-124">该函数返回的只进的枚举器。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="c1f9d-125">通常情况下，只进的枚举器速度更快，并使用较少的内存比传统的枚举器，但它们不允许对调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="c1f9d-126">0</span><span class="sxs-lookup"><span data-stu-id="c1f9d-126">0</span></span> | <span data-ttu-id="c1f9d-127">WMI 将保留指向 enumration 中对象的指针，直到它们被释放。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-127">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="c1f9d-128">建议的标志`WBEM_FLAG_RETURN_IMMEDIATELY`和`WBEM_FLAG_FORWARD_ONLY`为了获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="c1f9d-129">[in]通常情况下，此值是`null`。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="c1f9d-130">否则，它是一个指向[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)可能由提供的请求的实例的提供程序的实例。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-130">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`  
<span data-ttu-id="c1f9d-131">[out]接收对枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="c1f9d-132">[in]授权级别。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-132">[in] The authorization level.</span></span>

<span data-ttu-id="c1f9d-133">`impLevel` [in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-133">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="c1f9d-134">[in]一个指向[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象，表示当前命名空间。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-134">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="c1f9d-135">[in]用户名称。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-135">[in] The user name.</span></span> <span data-ttu-id="c1f9d-136">请参阅[ConnectServerWmi](connectserverwmi.md)函数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="c1f9d-137">[in]密码。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-137">[in] The password.</span></span> <span data-ttu-id="c1f9d-138">请参阅[ConnectServerWmi](connectserverwmi.md)函数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="c1f9d-139">[in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-139">[in] The domain name of the user.</span></span> <span data-ttu-id="c1f9d-140">请参阅[ConnectServerWmi](connectserverwmi.md)函数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="c1f9d-141">返回值</span><span class="sxs-lookup"><span data-stu-id="c1f9d-141">Return value</span></span>

<span data-ttu-id="c1f9d-142">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="c1f9d-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c1f9d-143">返回的常量</span><span class="sxs-lookup"><span data-stu-id="c1f9d-143">Constant</span></span>  |<span data-ttu-id="c1f9d-144">“值”</span><span class="sxs-lookup"><span data-stu-id="c1f9d-144">Value</span></span>  |<span data-ttu-id="c1f9d-145">描述</span><span class="sxs-lookup"><span data-stu-id="c1f9d-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="c1f9d-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="c1f9d-146">0x80041003</span></span> | <span data-ttu-id="c1f9d-147">用户没有权限查看的指定类的实例。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="c1f9d-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c1f9d-148">0x80041001</span></span> | <span data-ttu-id="c1f9d-149">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="c1f9d-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="c1f9d-150">0x80041010</span></span> | <span data-ttu-id="c1f9d-151">`strFilter` 不存在。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c1f9d-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c1f9d-152">0x80041008</span></span> | <span data-ttu-id="c1f9d-153">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c1f9d-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c1f9d-154">0x80041006</span></span> | <span data-ttu-id="c1f9d-155">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="c1f9d-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="c1f9d-156">0x80041033</span></span> | <span data-ttu-id="c1f9d-157">WMI 是可能已停止并重新启动。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="c1f9d-158">调用[ConnectServerWmi](connectserverwmi.md)试。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="c1f9d-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="c1f9d-159">0x80041015</span></span> | <span data-ttu-id="c1f9d-160">之间的当前进程和 WMI 的远程过程调用 (RPC) 链接已失败。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c1f9d-161">0</span><span class="sxs-lookup"><span data-stu-id="c1f9d-161">0</span></span> | <span data-ttu-id="c1f9d-162">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-162">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c1f9d-163">备注</span><span class="sxs-lookup"><span data-stu-id="c1f9d-163">Remarks</span></span>

<span data-ttu-id="c1f9d-164">此函数包装对的调用[iwbemservices:: Createclassenum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum)方法。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-164">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) method.</span></span>

<span data-ttu-id="c1f9d-165">请注意返回的枚举器可以具有零个元素。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="c1f9d-166">如果函数调用失败，则可以通过调用获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="c1f9d-167">要求</span><span class="sxs-lookup"><span data-stu-id="c1f9d-167">Requirements</span></span>  
 <span data-ttu-id="c1f9d-168">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1f9d-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1f9d-169">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c1f9d-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c1f9d-170">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c1f9d-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f9d-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1f9d-171">See also</span></span>
- [<span data-ttu-id="c1f9d-172">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="c1f9d-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
