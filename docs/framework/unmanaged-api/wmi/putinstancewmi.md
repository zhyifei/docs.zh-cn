---
title: PutInstanceWmi 函数（非托管 API 参考）
description: PutInstanceWmi 函数创建或更新现有类的实例。
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37810ecab2e02d4ec250dd2a4b2657c3b898f714
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798371"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="cc5e9-103">PutInstanceWmi 函数</span><span class="sxs-lookup"><span data-stu-id="cc5e9-103">PutInstanceWmi function</span></span>

<span data-ttu-id="cc5e9-104">创建或更新现有类的实例。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="cc5e9-105">将该实例写入 WMI 存储库。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="cc5e9-106">语法</span><span class="sxs-lookup"><span data-stu-id="cc5e9-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="cc5e9-107">参数</span><span class="sxs-lookup"><span data-stu-id="cc5e9-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="cc5e9-108">中指向要写入的实例的指针。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="cc5e9-109">中影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="cc5e9-110">以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="cc5e9-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cc5e9-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="cc5e9-111">Constant</span></span>  |<span data-ttu-id="cc5e9-112">值</span><span class="sxs-lookup"><span data-stu-id="cc5e9-112">Value</span></span>  |<span data-ttu-id="cc5e9-113">描述</span><span class="sxs-lookup"><span data-stu-id="cc5e9-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="cc5e9-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="cc5e9-114">0x20000</span></span> | <span data-ttu-id="cc5e9-115">如果已设置，WMI 不会将任何限定符存储在**修改**后的风格。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="cc5e9-116">如果未设置，则假定此对象未本地化，且所有限定符都与此实例一起存储。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="cc5e9-117">0</span><span class="sxs-lookup"><span data-stu-id="cc5e9-117">0</span></span> | <span data-ttu-id="cc5e9-118">如果实例不存在，请创建它，如果已存在，则覆盖它。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="cc5e9-119">1</span><span class="sxs-lookup"><span data-stu-id="cc5e9-119">1</span></span> | <span data-ttu-id="cc5e9-120">更新实例。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-120">Update the instance.</span></span> <span data-ttu-id="cc5e9-121">此实例必须存在，调用才能成功。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="cc5e9-122">2</span><span class="sxs-lookup"><span data-stu-id="cc5e9-122">2</span></span> | <span data-ttu-id="cc5e9-123">创建实例。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-123">Create the instance.</span></span> <span data-ttu-id="cc5e9-124">如果该实例已存在，则调用失败。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="cc5e9-125">0x10</span><span class="sxs-lookup"><span data-stu-id="cc5e9-125">0x10</span></span> | <span data-ttu-id="cc5e9-126">标志导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="cc5e9-127">中通常，此值为`null`。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="cc5e9-128">否则，它是指向提供请求的类的提供程序可以使用的[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="cc5e9-129">弄如果`null`为，则不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="cc5e9-130">如果`lFlags`包含`WBEM_FLAG_RETURN_IMMEDIATELY` ，`WBEM_S_NO_ERROR`则函数立即返回。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="cc5e9-131">`ppCallResult` 参数接收指向新 [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="cc5e9-132">返回值</span><span class="sxs-lookup"><span data-stu-id="cc5e9-132">Return value</span></span>

<span data-ttu-id="cc5e9-133">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="cc5e9-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cc5e9-134">返回的常量</span><span class="sxs-lookup"><span data-stu-id="cc5e9-134">Constant</span></span>  |<span data-ttu-id="cc5e9-135">值</span><span class="sxs-lookup"><span data-stu-id="cc5e9-135">Value</span></span>  |<span data-ttu-id="cc5e9-136">描述</span><span class="sxs-lookup"><span data-stu-id="cc5e9-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="cc5e9-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="cc5e9-137">0x80041003</span></span> | <span data-ttu-id="cc5e9-138">用户没有更新指定类的实例的权限。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="cc5e9-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="cc5e9-139">0x80041001</span></span> | <span data-ttu-id="cc5e9-140">发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="cc5e9-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="cc5e9-141">0x80041010</span></span> | <span data-ttu-id="cc5e9-142">支持此实例的类无效。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="cc5e9-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="cc5e9-143">0x80041028</span></span> | <span data-ttu-id="cc5e9-144">为`null`不能是`null`的属性指定了，例如，使用**索引**或**Not_Null**限定符标记的属性。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="cc5e9-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="cc5e9-145">0x8004100f</span></span> | <span data-ttu-id="cc5e9-146">指定的实例无效。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-146">The specified instance is not valid.</span></span> <span data-ttu-id="cc5e9-147">（例如，使用类`PutInstanceWmi`调用会返回此值。）</span><span class="sxs-lookup"><span data-stu-id="cc5e9-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cc5e9-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cc5e9-148">0x80041008</span></span> | <span data-ttu-id="cc5e9-149">参数无效。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="cc5e9-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="cc5e9-150">0x80041019</span></span> | <span data-ttu-id="cc5e9-151">已`WBEM_FLAG_CREATE_ONLY`指定标志，但该实例已存在。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="cc5e9-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="cc5e9-152">0x80041002</span></span> | <span data-ttu-id="cc5e9-153">`WBEM_FLAG_UPDATE_ONLY`已在中`lFlags`指定，但该实例不存在。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cc5e9-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cc5e9-154">0x80041006</span></span> | <span data-ttu-id="cc5e9-155">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="cc5e9-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="cc5e9-156">0x80041033</span></span> | <span data-ttu-id="cc5e9-157">WMI 可能已停止并重新启动。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="cc5e9-158">再次调用[ConnectServerWmi](connectserverwmi.md) 。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="cc5e9-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="cc5e9-159">0x80041015</span></span> | <span data-ttu-id="cc5e9-160">当前进程与 WMI 之间的远程过程调用（RPC）链接失败。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="cc5e9-161">0</span><span class="sxs-lookup"><span data-stu-id="cc5e9-161">0</span></span> | <span data-ttu-id="cc5e9-162">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cc5e9-163">备注</span><span class="sxs-lookup"><span data-stu-id="cc5e9-163">Remarks</span></span>

<span data-ttu-id="cc5e9-164">此函数包装对[IWbemServices：:P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="cc5e9-165">`PutInstanceWmi`函数仅支持创建实例和更新现有类的实例。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="cc5e9-166">根据`pCtx`参数的设置方式，将更新实例的部分或全部属性。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="cc5e9-167">当指向`pInst`的实例属于子类时，Windows Management 会调用所有负责派生子类的类的提供程序。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="cc5e9-168">所有这些提供程序必须成功，原始`PutInstanceWmi`请求才能成功。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="cc5e9-169">首先调用支持层次结构中最顶层的类的提供程序。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="cc5e9-170">调用顺序继续使用最顶层类的子类，并从上到下继续，直到 Windows 管理到达所属`pInst`的类的提供程序。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="cc5e9-171">Windows 管理不会为实例的任何子类调用提供程序。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="cc5e9-172">当应用程序必须更新属于类层次结构的实例时，该`pInst`参数必须指向包含要修改的属性的实例。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="cc5e9-173">也就是说，假设有一个属于**ClassB**的目标实例。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="cc5e9-174">**ClassB**实例派生自**ClassA**， **ClassA**定义属性**PropA**。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="cc5e9-175">如果应用程序要对**ClassB**实例中的`pInst` **PropA**值进行更改，则必须将其设置为该实例而不是**ClassA**的实例。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="cc5e9-176">不`PutInstanceWmi`允许在抽象类的实例上调用。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="cc5e9-177">如果函数调用失败，可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc5e9-178">要求</span><span class="sxs-lookup"><span data-stu-id="cc5e9-178">Requirements</span></span>

<span data-ttu-id="cc5e9-179">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc5e9-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="cc5e9-180">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cc5e9-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="cc5e9-181">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cc5e9-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cc5e9-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc5e9-182">See also</span></span>

- [<span data-ttu-id="cc5e9-183">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="cc5e9-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
