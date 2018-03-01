---
title: "ExecNotificationQueryWmi 函数 （非托管 API 参考）"
description: "ExecNotificationQueryWmi 函数执行一个查询来接收事件。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6dd0926d2262f8d0aa125b86755017a65a95a7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="8b7b6-103">ExecNotificationQueryWmi 函数</span><span class="sxs-lookup"><span data-stu-id="8b7b6-103">ExecNotificationQueryWmi function</span></span>
<span data-ttu-id="8b7b6-104">执行查询以接收事件。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-104">Executes a query to receive events.</span></span> <span data-ttu-id="8b7b6-105">调用立即返回，并且它们到达时，调用方可以轮询事件返回的枚举数。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="8b7b6-106">释放返回的枚举数取消查询。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-106">Releasing the returned enumerator cancels the query.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8b7b6-107">语法</span><span class="sxs-lookup"><span data-stu-id="8b7b6-107">Syntax</span></span>  
  
```  
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

## <a name="parameters"></a><span data-ttu-id="8b7b6-108">参数</span><span class="sxs-lookup"><span data-stu-id="8b7b6-108">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="8b7b6-109">[in]包含支持 Windows 管理的有效的查询语言的字符串。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="8b7b6-110">它必须是"WQL"，WMI 查询语言的首字母缩写。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="8b7b6-111">[in]查询的文本。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-111">[in] The text of the query.</span></span> <span data-ttu-id="8b7b6-112">此参数不能为`null`。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-112">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="8b7b6-113">[in]影响此函数的行为的以下两个标志的组合。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="8b7b6-114">在中定义这些值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> 

| <span data-ttu-id="8b7b6-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="8b7b6-115">Constant</span></span> | <span data-ttu-id="8b7b6-116">“值”</span><span class="sxs-lookup"><span data-stu-id="8b7b6-116">Value</span></span>  | <span data-ttu-id="8b7b6-117">描述</span><span class="sxs-lookup"><span data-stu-id="8b7b6-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="8b7b6-118">0x10</span><span class="sxs-lookup"><span data-stu-id="8b7b6-118">0x10</span></span> | <span data-ttu-id="8b7b6-119">标志会导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="8b7b6-120">如果未设置此标志，则调用将失败。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="8b7b6-121">这是因为事件接收连续，这意味着用户必须轮询返回的枚举数。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="8b7b6-122">无限期地阻止此调用，将无法进行。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="8b7b6-123">0x20</span><span class="sxs-lookup"><span data-stu-id="8b7b6-123">0x20</span></span> | <span data-ttu-id="8b7b6-124">该函数返回的只进的枚举器。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="8b7b6-125">通常，只进的枚举器速度更快和使用的内存少于传统枚举器，但它们不允许调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`  
<span data-ttu-id="8b7b6-126">[in]通常，此值是`null`。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="8b7b6-127">否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可由提供的请求的事件提供程序的实例。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-127">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested events.</span></span> 

`ppEnum`  
<span data-ttu-id="8b7b6-128">[out]如果未发生错误，接收到的枚举器允许调用方检索中查询的结果集的实例的指针。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="8b7b6-129">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="8b7b6-130">[in]授权级别中。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-130">[in] The authorization level.</span></span>

<span data-ttu-id="8b7b6-131">`impLevel`[in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-131">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="8b7b6-132">[in]指向的指针[IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx)对象，表示当前的命名空间。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-132">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="8b7b6-133">[in]用户名。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-133">[in] The user name.</span></span> <span data-ttu-id="8b7b6-134">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="8b7b6-135">[in]密码。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-135">[in] The password.</span></span> <span data-ttu-id="8b7b6-136">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="8b7b6-137">[in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-137">[in] The domain name of the user.</span></span> <span data-ttu-id="8b7b6-138">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="8b7b6-139">返回值</span><span class="sxs-lookup"><span data-stu-id="8b7b6-139">Return value</span></span>

<span data-ttu-id="8b7b6-140">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="8b7b6-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8b7b6-141">返回的常量</span><span class="sxs-lookup"><span data-stu-id="8b7b6-141">Constant</span></span>  |<span data-ttu-id="8b7b6-142">“值”</span><span class="sxs-lookup"><span data-stu-id="8b7b6-142">Value</span></span>  |<span data-ttu-id="8b7b6-143">描述</span><span class="sxs-lookup"><span data-stu-id="8b7b6-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="8b7b6-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="8b7b6-144">0x80041003</span></span> | <span data-ttu-id="8b7b6-145">用户没有权限查看一个或多个函数可以返回的类。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="8b7b6-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8b7b6-146">0x80041001</span></span> | <span data-ttu-id="8b7b6-147">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8b7b6-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8b7b6-148">0x80041008</span></span> | <span data-ttu-id="8b7b6-149">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="8b7b6-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="8b7b6-150">0x80041010</span></span> | <span data-ttu-id="8b7b6-151">查询指定不存在的类。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="8b7b6-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="8b7b6-152">0x80042002</span></span> | <span data-ttu-id="8b7b6-153">已请求中传递的事件太多精度。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="8b7b6-154">必须指定更大的轮询容差。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="8b7b6-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="8b7b6-155">0x80042001</span></span> | <span data-ttu-id="8b7b6-156">查询 requess 可以提供比 Windows 管理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-156">The query requess more information than Windows Management can provide.</span></span> <span data-ttu-id="8b7b6-157">这`HRESULT`事件查询导致轮询命名空间中的所有对象的请求时返回。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="8b7b6-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="8b7b6-158">0x80041017</span></span> | <span data-ttu-id="8b7b6-159">查询必须语法错误。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="8b7b6-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="8b7b6-160">0x80041018</span></span> | <span data-ttu-id="8b7b6-161">不支持请求的查询语言。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="8b7b6-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="8b7b6-162">0x8004106c</span></span> | <span data-ttu-id="8b7b6-163">查询太过复杂。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8b7b6-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8b7b6-164">0x80041006</span></span> | <span data-ttu-id="8b7b6-165">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="8b7b6-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="8b7b6-166">0x80041033</span></span> | <span data-ttu-id="8b7b6-167">WMI 时可能已停止和重新启动。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="8b7b6-168">调用[ConnectServerWmi](connectserverwmi.md)试。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="8b7b6-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="8b7b6-169">0x80041015</span></span> | <span data-ttu-id="8b7b6-170">之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="8b7b6-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="8b7b6-171">0x80041058</span></span> | <span data-ttu-id="8b7b6-172">无法分析查询。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8b7b6-173">0</span><span class="sxs-lookup"><span data-stu-id="8b7b6-173">0</span></span> | <span data-ttu-id="8b7b6-174">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-174">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8b7b6-175">备注</span><span class="sxs-lookup"><span data-stu-id="8b7b6-175">Remarks</span></span>

<span data-ttu-id="8b7b6-176">此函数包装对的调用[IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="8b7b6-177">该函数将返回后，调用方定期传递返回`ppEnum`对象传递给[下一步](next.md)函数以了解是否有任何事件。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="8b7b6-178">对于数没有限制`AND`和`OR`关键字可以在 WQL 查询中使用。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="8b7b6-179">大量复杂的查询中使用的 WQL 关键字可能会导致 WMI 返回`WBEM_E_QUOTA_VIOLATION`（或 0x8004106c） 错误代码为`HRESULT`值。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="8b7b6-180">WQL 关键字的限制取决于如何复杂查询是。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="8b7b6-181">如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b7b6-182">惠?</span><span class="sxs-lookup"><span data-stu-id="8b7b6-182">Requirements</span></span>  
 <span data-ttu-id="8b7b6-183">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b7b6-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b7b6-184">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8b7b6-184">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8b7b6-185">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8b7b6-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b7b6-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b7b6-186">See also</span></span>  
[<span data-ttu-id="8b7b6-187">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="8b7b6-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
