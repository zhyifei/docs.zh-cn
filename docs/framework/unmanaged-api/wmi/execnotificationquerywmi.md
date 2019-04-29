---
title: ExecNotificationQueryWmi 函数 （非托管 API 参考）
description: ExecNotificationQueryWmi 函数执行查询以接收事件。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cac00ff96d0c7007bdd6135282c3f767217385e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935611"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="6e87c-103">ExecNotificationQueryWmi 函数</span><span class="sxs-lookup"><span data-stu-id="6e87c-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="6e87c-104">执行查询以接收事件。</span><span class="sxs-lookup"><span data-stu-id="6e87c-104">Executes a query to receive events.</span></span> <span data-ttu-id="6e87c-105">调用立即返回，并且调用方可以轮询返回的枚举器的事件到达。</span><span class="sxs-lookup"><span data-stu-id="6e87c-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="6e87c-106">释放返回的枚举器取消查询。</span><span class="sxs-lookup"><span data-stu-id="6e87c-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6e87c-107">语法</span><span class="sxs-lookup"><span data-stu-id="6e87c-107">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="6e87c-108">参数</span><span class="sxs-lookup"><span data-stu-id="6e87c-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="6e87c-109">[in]具有支持的 Windows 管理的有效的查询语言的字符串。</span><span class="sxs-lookup"><span data-stu-id="6e87c-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="6e87c-110">它必须是"WQL"，WMI 查询语言的缩写词。</span><span class="sxs-lookup"><span data-stu-id="6e87c-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="6e87c-111">[in]查询的文本。</span><span class="sxs-lookup"><span data-stu-id="6e87c-111">[in] The text of the query.</span></span> <span data-ttu-id="6e87c-112">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="6e87c-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="6e87c-113">[in]影响此函数的行为的以下两个标志的组合。</span><span class="sxs-lookup"><span data-stu-id="6e87c-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="6e87c-114">这些值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中。</span><span class="sxs-lookup"><span data-stu-id="6e87c-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="6e87c-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="6e87c-115">Constant</span></span> | <span data-ttu-id="6e87c-116">“值”</span><span class="sxs-lookup"><span data-stu-id="6e87c-116">Value</span></span>  | <span data-ttu-id="6e87c-117">描述</span><span class="sxs-lookup"><span data-stu-id="6e87c-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="6e87c-118">0x10</span><span class="sxs-lookup"><span data-stu-id="6e87c-118">0x10</span></span> | <span data-ttu-id="6e87c-119">该标志会导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="6e87c-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="6e87c-120">如果未设置此标志，则调用失败。</span><span class="sxs-lookup"><span data-stu-id="6e87c-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="6e87c-121">这是因为事件接收连续，这意味着用户必须轮询返回的枚举器。</span><span class="sxs-lookup"><span data-stu-id="6e87c-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="6e87c-122">无限期地阻止此调用，将无法进行。</span><span class="sxs-lookup"><span data-stu-id="6e87c-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="6e87c-123">0x20</span><span class="sxs-lookup"><span data-stu-id="6e87c-123">0x20</span></span> | <span data-ttu-id="6e87c-124">该函数返回的只进的枚举器。</span><span class="sxs-lookup"><span data-stu-id="6e87c-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="6e87c-125">通常情况下，只进的枚举器速度更快，并使用较少的内存比传统的枚举器，但它们不允许对调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="6e87c-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="6e87c-126">[in]通常情况下，此值是`null`。</span><span class="sxs-lookup"><span data-stu-id="6e87c-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="6e87c-127">否则，它是一个指向[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)可由提供请求的事件提供程序的实例。</span><span class="sxs-lookup"><span data-stu-id="6e87c-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="6e87c-128">[out]如果未发生错误，接收允许调用方检索查询的结果集中的实例的枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="6e87c-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="6e87c-129">请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="6e87c-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="6e87c-130">[in]授权级别。</span><span class="sxs-lookup"><span data-stu-id="6e87c-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="6e87c-131">[in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="6e87c-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="6e87c-132">[in]一个指向[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象，表示当前命名空间。</span><span class="sxs-lookup"><span data-stu-id="6e87c-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="6e87c-133">[in]用户名称。</span><span class="sxs-lookup"><span data-stu-id="6e87c-133">[in] The user name.</span></span> <span data-ttu-id="6e87c-134">请参阅[ConnectServerWmi](connectserverwmi.md)函数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6e87c-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="6e87c-135">[in]密码。</span><span class="sxs-lookup"><span data-stu-id="6e87c-135">[in] The password.</span></span> <span data-ttu-id="6e87c-136">请参阅[ConnectServerWmi](connectserverwmi.md)函数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6e87c-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="6e87c-137">[in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="6e87c-137">[in] The domain name of the user.</span></span> <span data-ttu-id="6e87c-138">请参阅[ConnectServerWmi](connectserverwmi.md)函数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6e87c-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="6e87c-139">返回值</span><span class="sxs-lookup"><span data-stu-id="6e87c-139">Return value</span></span>

<span data-ttu-id="6e87c-140">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="6e87c-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6e87c-141">返回的常量</span><span class="sxs-lookup"><span data-stu-id="6e87c-141">Constant</span></span>  |<span data-ttu-id="6e87c-142">“值”</span><span class="sxs-lookup"><span data-stu-id="6e87c-142">Value</span></span>  |<span data-ttu-id="6e87c-143">描述</span><span class="sxs-lookup"><span data-stu-id="6e87c-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="6e87c-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="6e87c-144">0x80041003</span></span> | <span data-ttu-id="6e87c-145">用户没有权限查看一个或多个函数可以返回的类。</span><span class="sxs-lookup"><span data-stu-id="6e87c-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="6e87c-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6e87c-146">0x80041001</span></span> | <span data-ttu-id="6e87c-147">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="6e87c-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6e87c-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6e87c-148">0x80041008</span></span> | <span data-ttu-id="6e87c-149">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="6e87c-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="6e87c-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="6e87c-150">0x80041010</span></span> | <span data-ttu-id="6e87c-151">该查询指定不存在的类。</span><span class="sxs-lookup"><span data-stu-id="6e87c-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="6e87c-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="6e87c-152">0x80042002</span></span> | <span data-ttu-id="6e87c-153">已请求中传递的事件过多精度。</span><span class="sxs-lookup"><span data-stu-id="6e87c-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="6e87c-154">必须指定更大的轮询容差。</span><span class="sxs-lookup"><span data-stu-id="6e87c-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="6e87c-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="6e87c-155">0x80042001</span></span> | <span data-ttu-id="6e87c-156">查询请求比提供 Windows 管理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6e87c-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="6e87c-157">这`HRESULT`事件查询导致轮询一个命名空间中的所有对象的请求时返回。</span><span class="sxs-lookup"><span data-stu-id="6e87c-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="6e87c-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="6e87c-158">0x80041017</span></span> | <span data-ttu-id="6e87c-159">查询发生了语法错误。</span><span class="sxs-lookup"><span data-stu-id="6e87c-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="6e87c-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="6e87c-160">0x80041018</span></span> | <span data-ttu-id="6e87c-161">不支持请求的查询语言。</span><span class="sxs-lookup"><span data-stu-id="6e87c-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="6e87c-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="6e87c-162">0x8004106c</span></span> | <span data-ttu-id="6e87c-163">查询太过复杂。</span><span class="sxs-lookup"><span data-stu-id="6e87c-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6e87c-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6e87c-164">0x80041006</span></span> | <span data-ttu-id="6e87c-165">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="6e87c-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="6e87c-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="6e87c-166">0x80041033</span></span> | <span data-ttu-id="6e87c-167">WMI 是可能已停止并重新启动。</span><span class="sxs-lookup"><span data-stu-id="6e87c-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="6e87c-168">调用[ConnectServerWmi](connectserverwmi.md)试。</span><span class="sxs-lookup"><span data-stu-id="6e87c-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="6e87c-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="6e87c-169">0x80041015</span></span> | <span data-ttu-id="6e87c-170">之间的当前进程和 WMI 的远程过程调用 (RPC) 链接已失败。</span><span class="sxs-lookup"><span data-stu-id="6e87c-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="6e87c-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="6e87c-171">0x80041058</span></span> | <span data-ttu-id="6e87c-172">无法分析查询。</span><span class="sxs-lookup"><span data-stu-id="6e87c-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6e87c-173">0</span><span class="sxs-lookup"><span data-stu-id="6e87c-173">0</span></span> | <span data-ttu-id="6e87c-174">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="6e87c-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="6e87c-175">备注</span><span class="sxs-lookup"><span data-stu-id="6e87c-175">Remarks</span></span>

<span data-ttu-id="6e87c-176">此函数包装对的调用[IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery)方法。</span><span class="sxs-lookup"><span data-stu-id="6e87c-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="6e87c-177">该函数返回后，调用方定期传递返回`ppEnum`对象传递给[下一步](next.md)函数以了解是否有任何事件。</span><span class="sxs-lookup"><span data-stu-id="6e87c-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="6e87c-178">有数限制`AND`和`OR`可以在 WQL 查询中使用的关键字。</span><span class="sxs-lookup"><span data-stu-id="6e87c-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="6e87c-179">大量的复杂查询中使用的 WQL 关键字可能会导致 WMI 返回`WBEM_E_QUOTA_VIOLATION`（或 0x8004106c） 错误代码为`HRESULT`值。</span><span class="sxs-lookup"><span data-stu-id="6e87c-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="6e87c-180">WQL 关键字的限制取决于复杂的查询是。</span><span class="sxs-lookup"><span data-stu-id="6e87c-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="6e87c-181">如果函数调用失败，则可以通过调用获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="6e87c-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e87c-182">要求</span><span class="sxs-lookup"><span data-stu-id="6e87c-182">Requirements</span></span>

<span data-ttu-id="6e87c-183">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e87c-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6e87c-184">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6e87c-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="6e87c-185">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6e87c-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6e87c-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e87c-186">See also</span></span>

- [<span data-ttu-id="6e87c-187">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="6e87c-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)