---
title: ExecQueryWmi 函数（非托管 API 参考）
description: ExecQueryWmi 函数执行查询来检索对象。
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8547d306819e85b838f1160d9912dd43e42f2f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798684"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="fc7c3-103">ExecQueryWmi 函数</span><span class="sxs-lookup"><span data-stu-id="fc7c3-103">ExecQueryWmi function</span></span>

<span data-ttu-id="fc7c3-104">执行查询以检索对象。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fc7c3-105">语法</span><span class="sxs-lookup"><span data-stu-id="fc7c3-105">Syntax</span></span>

```cpp
HRESULT ExecQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
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

## <a name="parameters"></a><span data-ttu-id="fc7c3-106">参数</span><span class="sxs-lookup"><span data-stu-id="fc7c3-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="fc7c3-107">中具有 Windows 管理支持的有效查询语言的字符串。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="fc7c3-108">它必须是 "WQL" （WMI 查询语言的首字母缩写）。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="fc7c3-109">中查询的文本。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-109">[in] The text of the query.</span></span> <span data-ttu-id="fc7c3-110">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="fc7c3-111">中影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="fc7c3-112">以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="fc7c3-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="fc7c3-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="fc7c3-113">Constant</span></span> | <span data-ttu-id="fc7c3-114">值</span><span class="sxs-lookup"><span data-stu-id="fc7c3-114">Value</span></span>  | <span data-ttu-id="fc7c3-115">描述</span><span class="sxs-lookup"><span data-stu-id="fc7c3-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="fc7c3-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="fc7c3-116">0x20000</span></span> | <span data-ttu-id="fc7c3-117">如果设置，则函数将检索存储在当前连接的区域设置的本地化命名空间中的已修改限定符。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="fc7c3-118">如果未设置，则函数仅检索直接命名空间中存储的限定符。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="fc7c3-119">0x10</span><span class="sxs-lookup"><span data-stu-id="fc7c3-119">0x10</span></span> | <span data-ttu-id="fc7c3-120">标志导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="fc7c3-121">0x20</span><span class="sxs-lookup"><span data-stu-id="fc7c3-121">0x20</span></span> | <span data-ttu-id="fc7c3-122">函数返回一个只进枚举器。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="fc7c3-123">通常，只进枚举器比传统枚举器更快，使用的内存更少，但它们不允许调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="fc7c3-124">0</span><span class="sxs-lookup"><span data-stu-id="fc7c3-124">0</span></span> | <span data-ttu-id="fc7c3-125">WMI 保留指向枚举中的对象的指针，直到它们被释放。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="fc7c3-126">0x100</span><span class="sxs-lookup"><span data-stu-id="fc7c3-126">0x100</span></span> | <span data-ttu-id="fc7c3-127">确保返回的任何对象都有足够的信息， `null`以便不能使用系统属性，例如 **__PATH**、 **__RELPATH**和 **__SERVER**。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="fc7c3-128">2</span><span class="sxs-lookup"><span data-stu-id="fc7c3-128">2</span></span> | <span data-ttu-id="fc7c3-129">此标志用于原型制作。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-129">This flag is used for prototyping.</span></span> <span data-ttu-id="fc7c3-130">它不执行查询，而是返回类似于典型结果对象的对象。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="fc7c3-131">0x200</span><span class="sxs-lookup"><span data-stu-id="fc7c3-131">0x200</span></span> | <span data-ttu-id="fc7c3-132">导致为指定的类直接访问提供程序，而不考虑其父类或任何子类。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="fc7c3-133">建议的标志`WBEM_FLAG_RETURN_IMMEDIATELY`为， `WBEM_FLAG_FORWARD_ONLY`为获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="fc7c3-134">中通常，此值为`null`。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="fc7c3-135">否则，它是指向提供请求的类的提供程序可以使用的[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="fc7c3-136">弄如果未发生错误，则接收指向枚举器的指针，该枚举器允许调用方检索查询结果集中的实例。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="fc7c3-137">查询的结果集可以为零。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="fc7c3-138">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="fc7c3-139">中授权级别。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="fc7c3-140">中模拟级别。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="fc7c3-141">中指向表示当前命名空间的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="fc7c3-142">中用户名。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-142">[in] The user name.</span></span> <span data-ttu-id="fc7c3-143">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="fc7c3-144">中密码。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-144">[in] The password.</span></span> <span data-ttu-id="fc7c3-145">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="fc7c3-146">中用户的域名。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-146">[in] The domain name of the user.</span></span> <span data-ttu-id="fc7c3-147">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="fc7c3-148">返回值</span><span class="sxs-lookup"><span data-stu-id="fc7c3-148">Return value</span></span>

<span data-ttu-id="fc7c3-149">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="fc7c3-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fc7c3-150">返回的常量</span><span class="sxs-lookup"><span data-stu-id="fc7c3-150">Constant</span></span>  |<span data-ttu-id="fc7c3-151">值</span><span class="sxs-lookup"><span data-stu-id="fc7c3-151">Value</span></span>  |<span data-ttu-id="fc7c3-152">描述</span><span class="sxs-lookup"><span data-stu-id="fc7c3-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="fc7c3-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="fc7c3-153">0x80041003</span></span> | <span data-ttu-id="fc7c3-154">用户无权查看函数可以返回的一个或多个类。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="fc7c3-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="fc7c3-155">0x80041001</span></span> | <span data-ttu-id="fc7c3-156">发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fc7c3-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fc7c3-157">0x80041008</span></span> | <span data-ttu-id="fc7c3-158">参数无效。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="fc7c3-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="fc7c3-159">0x80041017</span></span> | <span data-ttu-id="fc7c3-160">查询具有语法错误。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="fc7c3-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="fc7c3-161">0x80041018</span></span> | <span data-ttu-id="fc7c3-162">不支持请求的查询语言。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="fc7c3-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="fc7c3-163">0x8004106c</span></span> | <span data-ttu-id="fc7c3-164">查询太复杂。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fc7c3-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fc7c3-165">0x80041006</span></span> | <span data-ttu-id="fc7c3-166">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="fc7c3-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="fc7c3-167">0x80041033</span></span> | <span data-ttu-id="fc7c3-168">WMI 可能已停止并重新启动。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="fc7c3-169">再次调用[ConnectServerWmi](connectserverwmi.md) 。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="fc7c3-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="fc7c3-170">0x80041015</span></span> | <span data-ttu-id="fc7c3-171">当前进程与 WMI 之间的远程过程调用（RPC）链接失败。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="fc7c3-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="fc7c3-172">0x80041002</span></span> | <span data-ttu-id="fc7c3-173">查询指定了一个不存在的类。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="fc7c3-174">0</span><span class="sxs-lookup"><span data-stu-id="fc7c3-174">0</span></span> | <span data-ttu-id="fc7c3-175">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="fc7c3-176">备注</span><span class="sxs-lookup"><span data-stu-id="fc7c3-176">Remarks</span></span>

<span data-ttu-id="fc7c3-177">此函数包装对[IWbemServices：： ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="fc7c3-178">此函数处理`strQuery`参数中指定的查询，并创建一个枚举器，调用方可以通过该枚举器访问查询结果。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="fc7c3-179">枚举器是指向[IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)接口的指针;查询结果是通过[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)接口提供的类对象的实例。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="fc7c3-180">可在 WQL 查询中使用的`AND`和`OR`关键字的数量有限制。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="fc7c3-181">复杂查询中使用大量的 WQL 关键字可能会导致 WMI 以`WBEM_E_QUOTA_VIOLATION` `HRESULT`值的形式返回（或0x8004106c）错误代码。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="fc7c3-182">WQL 关键字的限制取决于查询的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="fc7c3-183">如果函数调用失败，可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc7c3-184">要求</span><span class="sxs-lookup"><span data-stu-id="fc7c3-184">Requirements</span></span>

<span data-ttu-id="fc7c3-185">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc7c3-185">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="fc7c3-186">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fc7c3-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="fc7c3-187">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fc7c3-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fc7c3-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc7c3-188">See also</span></span>

- [<span data-ttu-id="fc7c3-189">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="fc7c3-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
