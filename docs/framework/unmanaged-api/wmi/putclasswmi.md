---
title: PutClassWmi 函数（非托管 API 参考）
description: PutClassWmi 函数将创建一个新类或更新现有的类。
ms.date: 11/06/2017
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
ms.openlocfilehash: 7fcf879705135e0093868b48580a37f9d46aa594
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798392"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="68467-103">PutClassWmi 函数</span><span class="sxs-lookup"><span data-stu-id="68467-103">PutClassWmi function</span></span>

<span data-ttu-id="68467-104">创建新类或更新现有类。</span><span class="sxs-lookup"><span data-stu-id="68467-104">Creates a new class or updates an existing one.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="68467-105">语法</span><span class="sxs-lookup"><span data-stu-id="68467-105">Syntax</span></span>

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="68467-106">参数</span><span class="sxs-lookup"><span data-stu-id="68467-106">Parameters</span></span>

`pObject`\
<span data-ttu-id="68467-107">中指向有效类定义的指针。</span><span class="sxs-lookup"><span data-stu-id="68467-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="68467-108">必须用所有必需的属性值正确地对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="68467-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`\
<span data-ttu-id="68467-109">中影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="68467-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="68467-110">以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="68467-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="68467-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="68467-111">Constant</span></span>  |<span data-ttu-id="68467-112">值</span><span class="sxs-lookup"><span data-stu-id="68467-112">Value</span></span>  |<span data-ttu-id="68467-113">描述</span><span class="sxs-lookup"><span data-stu-id="68467-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="68467-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="68467-114">0x20000</span></span> | <span data-ttu-id="68467-115">如果已设置，WMI 不会将任何限定符存储在修改后的风格。</span><span class="sxs-lookup"><span data-stu-id="68467-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> <br> <span data-ttu-id="68467-116">如果未设置，则假定此对象未本地化，且所有限定符都与此实例一起存储。</span><span class="sxs-lookup"><span data-stu-id="68467-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="68467-117">0</span><span class="sxs-lookup"><span data-stu-id="68467-117">0</span></span> | <span data-ttu-id="68467-118">如果类不存在，则创建它，如果已存在，则覆盖它。</span><span class="sxs-lookup"><span data-stu-id="68467-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="68467-119">1</span><span class="sxs-lookup"><span data-stu-id="68467-119">1</span></span> | <span data-ttu-id="68467-120">更新类。</span><span class="sxs-lookup"><span data-stu-id="68467-120">Update the class.</span></span> <span data-ttu-id="68467-121">类必须存在，调用才能成功。</span><span class="sxs-lookup"><span data-stu-id="68467-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="68467-122">2</span><span class="sxs-lookup"><span data-stu-id="68467-122">2</span></span> | <span data-ttu-id="68467-123">创建类。</span><span class="sxs-lookup"><span data-stu-id="68467-123">Create the class.</span></span> <span data-ttu-id="68467-124">如果类已存在，则调用失败。</span><span class="sxs-lookup"><span data-stu-id="68467-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="68467-125">0x10</span><span class="sxs-lookup"><span data-stu-id="68467-125">0x10</span></span> | <span data-ttu-id="68467-126">标志导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="68467-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="68467-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="68467-127">0x10000</span></span> | <span data-ttu-id="68467-128">在调用`PutClassWmi`时，推送提供程序必须指定此标志，以指示此类已更改。</span><span class="sxs-lookup"><span data-stu-id="68467-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="68467-129">0</span><span class="sxs-lookup"><span data-stu-id="68467-129">0</span></span> | <span data-ttu-id="68467-130">如果类没有派生类，并且没有该类的实例，则允许更新类。</span><span class="sxs-lookup"><span data-stu-id="68467-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="68467-131">如果更改只是不重要的限定符（例如描述限定符），则它还允许在所有情况下进行更新。</span><span class="sxs-lookup"><span data-stu-id="68467-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="68467-132">如果类有实例或更改属于重要限定符，则更新会失败。</span><span class="sxs-lookup"><span data-stu-id="68467-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="68467-133">0x20</span><span class="sxs-lookup"><span data-stu-id="68467-133">0x20</span></span> | <span data-ttu-id="68467-134">允许更新类（即使有子类），因为更改不会导致与子类冲突。</span><span class="sxs-lookup"><span data-stu-id="68467-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="68467-135">例如，此标志允许将新的属性添加到基类中，此基类先前未在任何子类中提到。</span><span class="sxs-lookup"><span data-stu-id="68467-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="68467-136">如果类有实例，则更新会失败。</span><span class="sxs-lookup"><span data-stu-id="68467-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="68467-137">0x40</span><span class="sxs-lookup"><span data-stu-id="68467-137">0x40</span></span> | <span data-ttu-id="68467-138">存在冲突的子类时强制更新类。</span><span class="sxs-lookup"><span data-stu-id="68467-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="68467-139">例如，如果类限定符是在子类中定义的，并且基类尝试添加与现有限定符冲突的同一个限定符，则此标志会强制进行更新。</span><span class="sxs-lookup"><span data-stu-id="68467-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with the existing one.</span></span> <span data-ttu-id="68467-140">在强制模式下，通过删除子类中的冲突限定符解决了 tis 冲突。</span><span class="sxs-lookup"><span data-stu-id="68467-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`\
<span data-ttu-id="68467-141">中通常，此值为`null`。</span><span class="sxs-lookup"><span data-stu-id="68467-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="68467-142">否则，它是指向提供请求的类的提供程序可以使用的[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="68467-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="68467-143">弄如果`null`为，则不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="68467-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="68467-144">如果`lFlags`包含`WBEM_FLAG_RETURN_IMMEDIATELY` ，`WBEM_S_NO_ERROR`则函数立即返回。</span><span class="sxs-lookup"><span data-stu-id="68467-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="68467-145">`ppCallResult`参数接收指向新 [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="68467-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="68467-146">返回值</span><span class="sxs-lookup"><span data-stu-id="68467-146">Return value</span></span>

<span data-ttu-id="68467-147">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="68467-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="68467-148">返回的常量</span><span class="sxs-lookup"><span data-stu-id="68467-148">Constant</span></span>  |<span data-ttu-id="68467-149">值</span><span class="sxs-lookup"><span data-stu-id="68467-149">Value</span></span>  |<span data-ttu-id="68467-150">描述</span><span class="sxs-lookup"><span data-stu-id="68467-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="68467-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="68467-151">0x80041003</span></span> | <span data-ttu-id="68467-152">用户没有创建或修改类的权限。</span><span class="sxs-lookup"><span data-stu-id="68467-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="68467-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="68467-153">0x80041001</span></span> | <span data-ttu-id="68467-154">发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="68467-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="68467-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="68467-155">0x80041010</span></span> | <span data-ttu-id="68467-156">指定的类无效。</span><span class="sxs-lookup"><span data-stu-id="68467-156">The specified class is not valid.</span></span> <span data-ttu-id="68467-157">通常，此指示`pObject`指定实例对象。</span><span class="sxs-lookup"><span data-stu-id="68467-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="68467-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="68467-158">0x80041008</span></span> | <span data-ttu-id="68467-159">参数无效。</span><span class="sxs-lookup"><span data-stu-id="68467-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="68467-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="68467-160">0x80041016</span></span> | <span data-ttu-id="68467-161">指定的类名无效。</span><span class="sxs-lookup"><span data-stu-id="68467-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="68467-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="68467-162">0x80041025</span></span> | <span data-ttu-id="68467-163">尝试进行的更改会使子类无效。</span><span class="sxs-lookup"><span data-stu-id="68467-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="68467-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="68467-164">0x80041019</span></span> | <span data-ttu-id="68467-165">已`WBEM_FLAG_CREATE_ONLY`指定标志，但该类已存在。</span><span class="sxs-lookup"><span data-stu-id="68467-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="68467-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="68467-166">0x80041002</span></span> | <span data-ttu-id="68467-167">`WBEM_FLAG_UPDATE_ONLY`在中`lFlags`指定了，并且找不到该类。</span><span class="sxs-lookup"><span data-stu-id="68467-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="68467-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="68467-168">0x80041020</span></span> | <span data-ttu-id="68467-169">尚未设置类的必需属性。</span><span class="sxs-lookup"><span data-stu-id="68467-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="68467-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="68467-170">0x80041006</span></span> | <span data-ttu-id="68467-171">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="68467-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="68467-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="68467-172">0x80041033</span></span> | <span data-ttu-id="68467-173">WMI 可能已停止并重新启动。</span><span class="sxs-lookup"><span data-stu-id="68467-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="68467-174">再次调用[ConnectServerWmi](connectserverwmi.md) 。</span><span class="sxs-lookup"><span data-stu-id="68467-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="68467-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="68467-175">0x80041015</span></span> | <span data-ttu-id="68467-176">当前进程与 WMI 之间的远程过程调用（RPC）链接失败。</span><span class="sxs-lookup"><span data-stu-id="68467-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="68467-177">0</span><span class="sxs-lookup"><span data-stu-id="68467-177">0</span></span> | <span data-ttu-id="68467-178">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="68467-178">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="68467-179">备注</span><span class="sxs-lookup"><span data-stu-id="68467-179">Remarks</span></span>

<span data-ttu-id="68467-180">此函数包装对[IWbemServices：:P utclass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="68467-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="68467-181">用户不能创建名称以下划线字符开头或结尾的类。</span><span class="sxs-lookup"><span data-stu-id="68467-181">The user may not create classes with names that begin or end with an underscore character.</span></span>

<span data-ttu-id="68467-182">如果函数调用失败，可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="68467-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="68467-183">要求</span><span class="sxs-lookup"><span data-stu-id="68467-183">Requirements</span></span>

<span data-ttu-id="68467-184">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68467-184">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="68467-185">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="68467-185">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="68467-186">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="68467-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="68467-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="68467-187">See also</span></span>

- [<span data-ttu-id="68467-188">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="68467-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
