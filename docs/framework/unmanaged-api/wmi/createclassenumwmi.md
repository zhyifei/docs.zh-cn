---
title: CreateClassEnumWmi 函数（非托管 API 参考）
description: CreateClassEnumWmi 函数为满足指定条件的所有类返回一个枚举器。
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1d637479bd140e635ee647a1e30d03343d8b0dcd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107522"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="d4f31-103">CreateClassEnumWmi 函数</span><span class="sxs-lookup"><span data-stu-id="d4f31-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="d4f31-104">返回满足指定选择条件的所有类的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d4f31-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d4f31-105">语法</span><span class="sxs-lookup"><span data-stu-id="d4f31-105">Syntax</span></span>

```cpp
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
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

## <a name="parameters"></a><span data-ttu-id="d4f31-106">参数</span><span class="sxs-lookup"><span data-stu-id="d4f31-106">Parameters</span></span>

`strSuperclass`\
<span data-ttu-id="d4f31-107">中如果不 `null` 或为空，则指定父类的名称;枚举器仅返回此类的子类。</span><span class="sxs-lookup"><span data-stu-id="d4f31-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="d4f31-108">如果 `null` 或为空且 `lFlags` 为 WBEM_FLAG_SHALLOW，则仅返回顶级类（没有父类的类）。</span><span class="sxs-lookup"><span data-stu-id="d4f31-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="d4f31-109">如果 `null` 或为空，并且 `lFlags` 为 `WBEM_FLAG_DEEP`，则返回命名空间中的所有类。</span><span class="sxs-lookup"><span data-stu-id="d4f31-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`\
<span data-ttu-id="d4f31-110">中影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="d4f31-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="d4f31-111">以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="d4f31-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d4f31-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="d4f31-112">Constant</span></span>  |<span data-ttu-id="d4f31-113">“值”</span><span class="sxs-lookup"><span data-stu-id="d4f31-113">Value</span></span>  |<span data-ttu-id="d4f31-114">描述</span><span class="sxs-lookup"><span data-stu-id="d4f31-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="d4f31-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="d4f31-115">0x20000</span></span> | <span data-ttu-id="d4f31-116">如果设置，则函数将检索存储在当前连接的区域设置的本地化命名空间中的已修改限定符。</span><span class="sxs-lookup"><span data-stu-id="d4f31-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="d4f31-117">如果未设置，则函数仅检索直接命名空间中存储的限定符。</span><span class="sxs-lookup"><span data-stu-id="d4f31-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="d4f31-118">0</span><span class="sxs-lookup"><span data-stu-id="d4f31-118">0</span></span> | <span data-ttu-id="d4f31-119">枚举包括层次结构中的所有子类，但不包括此类。</span><span class="sxs-lookup"><span data-stu-id="d4f31-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="d4f31-120">1</span><span class="sxs-lookup"><span data-stu-id="d4f31-120">1</span></span> | <span data-ttu-id="d4f31-121">枚举仅包括此类的纯实例，并排除提供此类中未找到的属性的所有子类的实例。</span><span class="sxs-lookup"><span data-stu-id="d4f31-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="d4f31-122">0x10</span><span class="sxs-lookup"><span data-stu-id="d4f31-122">0x10</span></span> | <span data-ttu-id="d4f31-123">标志导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="d4f31-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="d4f31-124">0x20</span><span class="sxs-lookup"><span data-stu-id="d4f31-124">0x20</span></span> | <span data-ttu-id="d4f31-125">函数返回一个只进枚举器。</span><span class="sxs-lookup"><span data-stu-id="d4f31-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="d4f31-126">通常，只进枚举器比传统枚举器更快，使用的内存更少，但它们不允许调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="d4f31-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="d4f31-127">0</span><span class="sxs-lookup"><span data-stu-id="d4f31-127">0</span></span> | <span data-ttu-id="d4f31-128">WMI 保留指向枚举中的对象的指针，直到它们被释放。</span><span class="sxs-lookup"><span data-stu-id="d4f31-128">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="d4f31-129">为了获得最佳性能，建议使用 `WBEM_FLAG_RETURN_IMMEDIATELY` 和 `WBEM_FLAG_FORWARD_ONLY`。</span><span class="sxs-lookup"><span data-stu-id="d4f31-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="d4f31-130">中通常，此值是 `null`的。</span><span class="sxs-lookup"><span data-stu-id="d4f31-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="d4f31-131">否则，它是指向提供请求的类的提供程序可以使用的[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="d4f31-131">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="d4f31-132">弄接收指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="d4f31-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="d4f31-133">中授权级别。</span><span class="sxs-lookup"><span data-stu-id="d4f31-133">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="d4f31-134">中模拟级别。</span><span class="sxs-lookup"><span data-stu-id="d4f31-134">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="d4f31-135">中指向表示当前命名空间的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d4f31-135">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="d4f31-136">中用户名。</span><span class="sxs-lookup"><span data-stu-id="d4f31-136">[in] The user name.</span></span> <span data-ttu-id="d4f31-137">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d4f31-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="d4f31-138">中密码。</span><span class="sxs-lookup"><span data-stu-id="d4f31-138">[in] The password.</span></span> <span data-ttu-id="d4f31-139">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d4f31-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="d4f31-140">中用户的域名。</span><span class="sxs-lookup"><span data-stu-id="d4f31-140">[in] The domain name of the user.</span></span> <span data-ttu-id="d4f31-141">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d4f31-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="d4f31-142">返回值</span><span class="sxs-lookup"><span data-stu-id="d4f31-142">Return value</span></span>

<span data-ttu-id="d4f31-143">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="d4f31-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d4f31-144">返回的常量</span><span class="sxs-lookup"><span data-stu-id="d4f31-144">Constant</span></span>  |<span data-ttu-id="d4f31-145">“值”</span><span class="sxs-lookup"><span data-stu-id="d4f31-145">Value</span></span>  |<span data-ttu-id="d4f31-146">描述</span><span class="sxs-lookup"><span data-stu-id="d4f31-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="d4f31-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="d4f31-147">0x80041003</span></span> | <span data-ttu-id="d4f31-148">用户无权查看函数可以返回的一个或多个类。</span><span class="sxs-lookup"><span data-stu-id="d4f31-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="d4f31-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d4f31-149">0x80041001</span></span> | <span data-ttu-id="d4f31-150">发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="d4f31-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="d4f31-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="d4f31-151">0x80041010</span></span> | <span data-ttu-id="d4f31-152">`strSuperClass` 不存在。</span><span class="sxs-lookup"><span data-stu-id="d4f31-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d4f31-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d4f31-153">0x80041008</span></span> | <span data-ttu-id="d4f31-154">参数无效。</span><span class="sxs-lookup"><span data-stu-id="d4f31-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d4f31-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d4f31-155">0x80041006</span></span> | <span data-ttu-id="d4f31-156">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="d4f31-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="d4f31-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="d4f31-157">0x80041033</span></span> | <span data-ttu-id="d4f31-158">WMI 可能已停止并重新启动。</span><span class="sxs-lookup"><span data-stu-id="d4f31-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="d4f31-159">再次调用[ConnectServerWmi](connectserverwmi.md) 。</span><span class="sxs-lookup"><span data-stu-id="d4f31-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="d4f31-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="d4f31-160">0x80041015</span></span> | <span data-ttu-id="d4f31-161">当前进程与 WMI 之间的远程过程调用（RPC）链接失败。</span><span class="sxs-lookup"><span data-stu-id="d4f31-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d4f31-162">0</span><span class="sxs-lookup"><span data-stu-id="d4f31-162">0</span></span> | <span data-ttu-id="d4f31-163">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="d4f31-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="d4f31-164">备注</span><span class="sxs-lookup"><span data-stu-id="d4f31-164">Remarks</span></span>

<span data-ttu-id="d4f31-165">此函数包装对[IWbemServices：： CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="d4f31-165">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) method.</span></span>

<span data-ttu-id="d4f31-166">如果函数调用失败，可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="d4f31-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="d4f31-167">要求</span><span class="sxs-lookup"><span data-stu-id="d4f31-167">Requirements</span></span>

<span data-ttu-id="d4f31-168">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4f31-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d4f31-169">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="d4f31-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d4f31-170">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f31-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d4f31-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4f31-171">See also</span></span>

- [<span data-ttu-id="d4f31-172">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="d4f31-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
