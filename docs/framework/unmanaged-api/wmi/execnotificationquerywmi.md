---
title: ExecNotificationQueryWmi 函数（非托管 API 参考）
description: ExecNotificationQueryWmi 函数执行查询来接收事件。
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3d8a7683eef52a5e91bf7aa84d5aa7db7dbdac8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130440"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="ea5cc-103">ExecNotificationQueryWmi 函数</span><span class="sxs-lookup"><span data-stu-id="ea5cc-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="ea5cc-104">执行查询以接收事件。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-104">Executes a query to receive events.</span></span> <span data-ttu-id="ea5cc-105">调用会立即返回，并且调用方可以在返回的事件发生时轮询返回的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="ea5cc-106">释放返回的枚举器将取消查询。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ea5cc-107">语法</span><span class="sxs-lookup"><span data-stu-id="ea5cc-107">Syntax</span></span>

```cpp
HRESULT ExecNotificationQueryWmi (
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

## <a name="parameters"></a><span data-ttu-id="ea5cc-108">参数</span><span class="sxs-lookup"><span data-stu-id="ea5cc-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="ea5cc-109">中具有 Windows 管理支持的有效查询语言的字符串。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="ea5cc-110">它必须是 "WQL" （WMI 查询语言的首字母缩写）。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="ea5cc-111">中查询的文本。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-111">[in] The text of the query.</span></span> <span data-ttu-id="ea5cc-112">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="ea5cc-113">中影响此函数的行为的以下两个标志的组合。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="ea5cc-114">这些值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="ea5cc-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="ea5cc-115">Constant</span></span> | <span data-ttu-id="ea5cc-116">“值”</span><span class="sxs-lookup"><span data-stu-id="ea5cc-116">Value</span></span>  | <span data-ttu-id="ea5cc-117">描述</span><span class="sxs-lookup"><span data-stu-id="ea5cc-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="ea5cc-118">0x10</span><span class="sxs-lookup"><span data-stu-id="ea5cc-118">0x10</span></span> | <span data-ttu-id="ea5cc-119">标志导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="ea5cc-120">如果未设置此标志，则调用失败。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="ea5cc-121">这是因为事件连续接收，这意味着用户必须轮询返回的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="ea5cc-122">无限期地阻止此调用会导致无法做到这一点。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="ea5cc-123">0x20</span><span class="sxs-lookup"><span data-stu-id="ea5cc-123">0x20</span></span> | <span data-ttu-id="ea5cc-124">函数返回一个只进枚举器。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="ea5cc-125">通常，只进枚举器比传统枚举器更快，使用的内存更少，但它们不允许调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="ea5cc-126">中通常，此值是 `null`的。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="ea5cc-127">否则，它是指向提供请求事件的提供程序可以使用的[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="ea5cc-128">弄如果未发生错误，则接收指向枚举器的指针，该枚举器允许调用方检索查询结果集中的实例。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="ea5cc-129">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="ea5cc-130">中授权级别。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="ea5cc-131">中模拟级别。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="ea5cc-132">中指向表示当前命名空间的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="ea5cc-133">中用户名。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-133">[in] The user name.</span></span> <span data-ttu-id="ea5cc-134">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="ea5cc-135">中密码。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-135">[in] The password.</span></span> <span data-ttu-id="ea5cc-136">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="ea5cc-137">中用户的域名。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-137">[in] The domain name of the user.</span></span> <span data-ttu-id="ea5cc-138">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="ea5cc-139">返回值</span><span class="sxs-lookup"><span data-stu-id="ea5cc-139">Return value</span></span>

<span data-ttu-id="ea5cc-140">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="ea5cc-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ea5cc-141">返回的常量</span><span class="sxs-lookup"><span data-stu-id="ea5cc-141">Constant</span></span>  |<span data-ttu-id="ea5cc-142">“值”</span><span class="sxs-lookup"><span data-stu-id="ea5cc-142">Value</span></span>  |<span data-ttu-id="ea5cc-143">描述</span><span class="sxs-lookup"><span data-stu-id="ea5cc-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="ea5cc-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="ea5cc-144">0x80041003</span></span> | <span data-ttu-id="ea5cc-145">用户无权查看函数可以返回的一个或多个类。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="ea5cc-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ea5cc-146">0x80041001</span></span> | <span data-ttu-id="ea5cc-147">发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ea5cc-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ea5cc-148">0x80041008</span></span> | <span data-ttu-id="ea5cc-149">参数无效。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="ea5cc-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="ea5cc-150">0x80041010</span></span> | <span data-ttu-id="ea5cc-151">查询指定了一个不存在的类。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="ea5cc-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="ea5cc-152">0x80042002</span></span> | <span data-ttu-id="ea5cc-153">请求传递事件的精度太多。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="ea5cc-154">必须指定较大的轮询容差。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="ea5cc-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="ea5cc-155">0x80042001</span></span> | <span data-ttu-id="ea5cc-156">查询请求的信息比 Windows 管理提供的信息多。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="ea5cc-157">当事件查询导致请求轮询命名空间中的所有对象时，将返回此 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="ea5cc-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="ea5cc-158">0x80041017</span></span> | <span data-ttu-id="ea5cc-159">查询具有语法错误。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="ea5cc-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="ea5cc-160">0x80041018</span></span> | <span data-ttu-id="ea5cc-161">不支持请求的查询语言。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="ea5cc-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="ea5cc-162">0x8004106c</span></span> | <span data-ttu-id="ea5cc-163">查询太复杂。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ea5cc-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ea5cc-164">0x80041006</span></span> | <span data-ttu-id="ea5cc-165">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="ea5cc-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="ea5cc-166">0x80041033</span></span> | <span data-ttu-id="ea5cc-167">WMI 可能已停止并重新启动。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="ea5cc-168">再次调用[ConnectServerWmi](connectserverwmi.md) 。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="ea5cc-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="ea5cc-169">0x80041015</span></span> | <span data-ttu-id="ea5cc-170">当前进程与 WMI 之间的远程过程调用（RPC）链接失败。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="ea5cc-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="ea5cc-171">0x80041058</span></span> | <span data-ttu-id="ea5cc-172">无法分析该查询。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ea5cc-173">0</span><span class="sxs-lookup"><span data-stu-id="ea5cc-173">0</span></span> | <span data-ttu-id="ea5cc-174">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ea5cc-175">备注</span><span class="sxs-lookup"><span data-stu-id="ea5cc-175">Remarks</span></span>

<span data-ttu-id="ea5cc-176">此函数包装对[IWbemServices：： ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="ea5cc-177">函数返回后，调用方定期将返回的 `ppEnum` 对象传递到[下一个](next.md)函数，以查看是否有可用的事件。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="ea5cc-178">可用于 WQL 查询的 `AND` 和 `OR` 关键字的数量有限制。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="ea5cc-179">复杂查询中使用大量的 WQL 关键字可能导致 WMI 以 `HRESULT` 值的形式返回 `WBEM_E_QUOTA_VIOLATION` （或0x8004106c）错误代码。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="ea5cc-180">WQL 关键字的限制取决于查询的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="ea5cc-181">如果函数调用失败，可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea5cc-182">要求</span><span class="sxs-lookup"><span data-stu-id="ea5cc-182">Requirements</span></span>

<span data-ttu-id="ea5cc-183">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea5cc-183">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ea5cc-184">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="ea5cc-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ea5cc-185">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ea5cc-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ea5cc-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea5cc-186">See also</span></span>

- [<span data-ttu-id="ea5cc-187">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="ea5cc-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
