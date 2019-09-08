---
title: CreateInstanceEnumWmi 函数（非托管 API 参考）
description: CreateInstanceEnumWmi 函数返回一个枚举数，该枚举数包含符合选择条件的指定类的实例。
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
ms.openlocfilehash: b7709d9c50a494013ece2f91b3acc213278f0e57
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798904"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="e1c68-103">CreateInstanceEnumWmi 函数</span><span class="sxs-lookup"><span data-stu-id="e1c68-103">CreateInstanceEnumWmi function</span></span>

<span data-ttu-id="e1c68-104">返回枚举器，该枚举器返回符合指定选择条件的指定类的实例。</span><span class="sxs-lookup"><span data-stu-id="e1c68-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e1c68-105">语法</span><span class="sxs-lookup"><span data-stu-id="e1c68-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="e1c68-106">参数</span><span class="sxs-lookup"><span data-stu-id="e1c68-106">Parameters</span></span>

`strFilter`\
<span data-ttu-id="e1c68-107">中需要其实例的类的名称。</span><span class="sxs-lookup"><span data-stu-id="e1c68-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="e1c68-108">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="e1c68-108">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="e1c68-109">中影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="e1c68-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="e1c68-110">以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="e1c68-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e1c68-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e1c68-111">Constant</span></span>  |<span data-ttu-id="e1c68-112">值</span><span class="sxs-lookup"><span data-stu-id="e1c68-112">Value</span></span>  |<span data-ttu-id="e1c68-113">描述</span><span class="sxs-lookup"><span data-stu-id="e1c68-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="e1c68-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="e1c68-114">0x20000</span></span> | <span data-ttu-id="e1c68-115">如果设置，则函数将检索存储在当前连接的区域设置的本地化命名空间中的已修改限定符。</span><span class="sxs-lookup"><span data-stu-id="e1c68-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="e1c68-116">如果未设置，则函数仅检索直接命名空间中存储的限定符。</span><span class="sxs-lookup"><span data-stu-id="e1c68-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="e1c68-117">0</span><span class="sxs-lookup"><span data-stu-id="e1c68-117">0</span></span> | <span data-ttu-id="e1c68-118">枚举包括此层次结构中的此和所有子类。</span><span class="sxs-lookup"><span data-stu-id="e1c68-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="e1c68-119">1</span><span class="sxs-lookup"><span data-stu-id="e1c68-119">1</span></span> | <span data-ttu-id="e1c68-120">枚举仅包括此类的纯实例，并排除提供此类中未找到的属性的所有子类的实例。</span><span class="sxs-lookup"><span data-stu-id="e1c68-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="e1c68-121">0x10</span><span class="sxs-lookup"><span data-stu-id="e1c68-121">0x10</span></span> | <span data-ttu-id="e1c68-122">标志导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="e1c68-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="e1c68-123">0x20</span><span class="sxs-lookup"><span data-stu-id="e1c68-123">0x20</span></span> | <span data-ttu-id="e1c68-124">函数返回一个只进枚举器。</span><span class="sxs-lookup"><span data-stu-id="e1c68-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="e1c68-125">通常，只进枚举器比传统枚举器更快，使用的内存更少，但它们不允许调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="e1c68-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="e1c68-126">0</span><span class="sxs-lookup"><span data-stu-id="e1c68-126">0</span></span> | <span data-ttu-id="e1c68-127">WMI 保留指向枚举中的对象的指针，直到它们被释放。</span><span class="sxs-lookup"><span data-stu-id="e1c68-127">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="e1c68-128">建议的标志`WBEM_FLAG_RETURN_IMMEDIATELY`为， `WBEM_FLAG_FORWARD_ONLY`为获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="e1c68-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="e1c68-129">中通常，此值为`null`。</span><span class="sxs-lookup"><span data-stu-id="e1c68-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="e1c68-130">否则，它是指向提供请求实例的提供程序可能使用的[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="e1c68-130">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`\
<span data-ttu-id="e1c68-131">弄接收指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="e1c68-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="e1c68-132">中授权级别。</span><span class="sxs-lookup"><span data-stu-id="e1c68-132">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="e1c68-133">中模拟级别。</span><span class="sxs-lookup"><span data-stu-id="e1c68-133">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="e1c68-134">中指向表示当前命名空间的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e1c68-134">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="e1c68-135">中用户名。</span><span class="sxs-lookup"><span data-stu-id="e1c68-135">[in] The user name.</span></span> <span data-ttu-id="e1c68-136">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="e1c68-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="e1c68-137">中密码。</span><span class="sxs-lookup"><span data-stu-id="e1c68-137">[in] The password.</span></span> <span data-ttu-id="e1c68-138">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="e1c68-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="e1c68-139">中用户的域名。</span><span class="sxs-lookup"><span data-stu-id="e1c68-139">[in] The domain name of the user.</span></span> <span data-ttu-id="e1c68-140">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="e1c68-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="e1c68-141">返回值</span><span class="sxs-lookup"><span data-stu-id="e1c68-141">Return value</span></span>

<span data-ttu-id="e1c68-142">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="e1c68-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e1c68-143">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e1c68-143">Constant</span></span>  |<span data-ttu-id="e1c68-144">值</span><span class="sxs-lookup"><span data-stu-id="e1c68-144">Value</span></span>  |<span data-ttu-id="e1c68-145">描述</span><span class="sxs-lookup"><span data-stu-id="e1c68-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="e1c68-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="e1c68-146">0x80041003</span></span> | <span data-ttu-id="e1c68-147">用户不具有查看指定类的实例的权限。</span><span class="sxs-lookup"><span data-stu-id="e1c68-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="e1c68-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e1c68-148">0x80041001</span></span> | <span data-ttu-id="e1c68-149">发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="e1c68-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="e1c68-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="e1c68-150">0x80041010</span></span> | <span data-ttu-id="e1c68-151">`strFilter` 不存在。</span><span class="sxs-lookup"><span data-stu-id="e1c68-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e1c68-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e1c68-152">0x80041008</span></span> | <span data-ttu-id="e1c68-153">参数无效。</span><span class="sxs-lookup"><span data-stu-id="e1c68-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e1c68-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e1c68-154">0x80041006</span></span> | <span data-ttu-id="e1c68-155">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="e1c68-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="e1c68-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="e1c68-156">0x80041033</span></span> | <span data-ttu-id="e1c68-157">WMI 可能已停止并重新启动。</span><span class="sxs-lookup"><span data-stu-id="e1c68-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="e1c68-158">再次调用[ConnectServerWmi](connectserverwmi.md) 。</span><span class="sxs-lookup"><span data-stu-id="e1c68-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="e1c68-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="e1c68-159">0x80041015</span></span> | <span data-ttu-id="e1c68-160">当前进程与 WMI 之间的远程过程调用（RPC）链接失败。</span><span class="sxs-lookup"><span data-stu-id="e1c68-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e1c68-161">0</span><span class="sxs-lookup"><span data-stu-id="e1c68-161">0</span></span> | <span data-ttu-id="e1c68-162">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e1c68-162">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e1c68-163">备注</span><span class="sxs-lookup"><span data-stu-id="e1c68-163">Remarks</span></span>

<span data-ttu-id="e1c68-164">此函数包装对[IWbemServices：： CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="e1c68-164">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) method.</span></span>

<span data-ttu-id="e1c68-165">请注意，返回的枚举器可以有零个元素。</span><span class="sxs-lookup"><span data-stu-id="e1c68-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="e1c68-166">如果函数调用失败，可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="e1c68-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1c68-167">要求</span><span class="sxs-lookup"><span data-stu-id="e1c68-167">Requirements</span></span>

<span data-ttu-id="e1c68-168">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1c68-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e1c68-169">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e1c68-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e1c68-170">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e1c68-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e1c68-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1c68-171">See also</span></span>

- [<span data-ttu-id="e1c68-172">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e1c68-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
