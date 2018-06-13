---
title: ExecQueryWmi 函数 （非托管 API 参考）
description: ExecQueryWmi 函数执行查询以检索对象。
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
ms.openlocfilehash: b482f2ca2e2d5c06e69945adb71aa6c0f5d26465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462086"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="36f55-103">ExecQueryWmi 函数</span><span class="sxs-lookup"><span data-stu-id="36f55-103">ExecQueryWmi function</span></span>
<span data-ttu-id="36f55-104">执行查询以检索对象。</span><span class="sxs-lookup"><span data-stu-id="36f55-104">Executes a query to retrieve objects.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="36f55-105">语法</span><span class="sxs-lookup"><span data-stu-id="36f55-105">Syntax</span></span>  
  
```  
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

## <a name="parameters"></a><span data-ttu-id="36f55-106">参数</span><span class="sxs-lookup"><span data-stu-id="36f55-106">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="36f55-107">[in]包含支持 Windows 管理的有效的查询语言的字符串。</span><span class="sxs-lookup"><span data-stu-id="36f55-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="36f55-108">它必须是"WQL"，WMI 查询语言的首字母缩写。</span><span class="sxs-lookup"><span data-stu-id="36f55-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="36f55-109">[in]查询的文本。</span><span class="sxs-lookup"><span data-stu-id="36f55-109">[in] The text of the query.</span></span> <span data-ttu-id="36f55-110">此参数不能为`null`。</span><span class="sxs-lookup"><span data-stu-id="36f55-110">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="36f55-111">[in]影响此函数的行为的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="36f55-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="36f55-112">在中定义以下值*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="36f55-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

| <span data-ttu-id="36f55-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="36f55-113">Constant</span></span> | <span data-ttu-id="36f55-114">值</span><span class="sxs-lookup"><span data-stu-id="36f55-114">Value</span></span>  | <span data-ttu-id="36f55-115">描述</span><span class="sxs-lookup"><span data-stu-id="36f55-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="36f55-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="36f55-116">0x20000</span></span> | <span data-ttu-id="36f55-117">如果集，该函数检索当前连接的区域设置的本地化命名空间中存储的修正的限定符。</span><span class="sxs-lookup"><span data-stu-id="36f55-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="36f55-118">如果未设置，函数将检索存储在即时命名空间限定符。</span><span class="sxs-lookup"><span data-stu-id="36f55-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="36f55-119">0x10</span><span class="sxs-lookup"><span data-stu-id="36f55-119">0x10</span></span> | <span data-ttu-id="36f55-120">标志会导致半同步调用。</span><span class="sxs-lookup"><span data-stu-id="36f55-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="36f55-121">0x20</span><span class="sxs-lookup"><span data-stu-id="36f55-121">0x20</span></span> | <span data-ttu-id="36f55-122">该函数返回的只进的枚举器。</span><span class="sxs-lookup"><span data-stu-id="36f55-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="36f55-123">通常，只进的枚举器速度更快和使用的内存少于传统枚举器，但它们不允许调用[克隆](clone.md)。</span><span class="sxs-lookup"><span data-stu-id="36f55-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="36f55-124">0</span><span class="sxs-lookup"><span data-stu-id="36f55-124">0</span></span> | <span data-ttu-id="36f55-125">WMI 将保留指向 enumration 中的对象的指针，直到它们被释放为止。</span><span class="sxs-lookup"><span data-stu-id="36f55-125">WMI retains pointers to objects in the enumration until they are released.</span></span> | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="36f55-126">0x100</span><span class="sxs-lookup"><span data-stu-id="36f55-126">0x100</span></span> | <span data-ttu-id="36f55-127">确保任何返回的对象中都有足够的信息，因此该系统属性，如 **__PATH**， **__RELPATH**，和 **__SERVER**，不是`null`。</span><span class="sxs-lookup"><span data-stu-id="36f55-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="36f55-128">2</span><span class="sxs-lookup"><span data-stu-id="36f55-128">2</span></span> | <span data-ttu-id="36f55-129">此标志用于原型制作。</span><span class="sxs-lookup"><span data-stu-id="36f55-129">This flag is used for prototyping.</span></span> <span data-ttu-id="36f55-130">它不会执行查询，并改为返回的对象，如下所示的典型结果对象。</span><span class="sxs-lookup"><span data-stu-id="36f55-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="36f55-131">0x200</span><span class="sxs-lookup"><span data-stu-id="36f55-131">0x200</span></span> | <span data-ttu-id="36f55-132">原因直接访问提供程序而不考虑其父类或任何子类指定的类。</span><span class="sxs-lookup"><span data-stu-id="36f55-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="36f55-133">建议的标志是`WBEM_FLAG_RETURN_IMMEDIATELY`和`WBEM_FLAG_FORWARD_ONLY`为了获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="36f55-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="36f55-134">[in]通常，此值是`null`。</span><span class="sxs-lookup"><span data-stu-id="36f55-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="36f55-135">否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx)可用的提供程序提供请求的类的实例。</span><span class="sxs-lookup"><span data-stu-id="36f55-135">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="36f55-136">[out]如果未发生错误，接收到的枚举器允许调用方检索中查询的结果集的实例的指针。</span><span class="sxs-lookup"><span data-stu-id="36f55-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="36f55-137">查询可以具有零个实例的结果集。</span><span class="sxs-lookup"><span data-stu-id="36f55-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="36f55-138">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="36f55-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="36f55-139">[in]授权级别中。</span><span class="sxs-lookup"><span data-stu-id="36f55-139">[in] The authorization level.</span></span>

<span data-ttu-id="36f55-140">`impLevel` [in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="36f55-140">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="36f55-141">[in]指向的指针[IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx)对象，表示当前的命名空间。</span><span class="sxs-lookup"><span data-stu-id="36f55-141">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="36f55-142">[in]用户名。</span><span class="sxs-lookup"><span data-stu-id="36f55-142">[in] The user name.</span></span> <span data-ttu-id="36f55-143">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="36f55-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="36f55-144">[in]密码。</span><span class="sxs-lookup"><span data-stu-id="36f55-144">[in] The password.</span></span> <span data-ttu-id="36f55-145">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="36f55-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="36f55-146">[in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="36f55-146">[in] The domain name of the user.</span></span> <span data-ttu-id="36f55-147">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="36f55-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="36f55-148">返回值</span><span class="sxs-lookup"><span data-stu-id="36f55-148">Return value</span></span>

<span data-ttu-id="36f55-149">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="36f55-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="36f55-150">返回的常量</span><span class="sxs-lookup"><span data-stu-id="36f55-150">Constant</span></span>  |<span data-ttu-id="36f55-151">值</span><span class="sxs-lookup"><span data-stu-id="36f55-151">Value</span></span>  |<span data-ttu-id="36f55-152">描述</span><span class="sxs-lookup"><span data-stu-id="36f55-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="36f55-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="36f55-153">0x80041003</span></span> | <span data-ttu-id="36f55-154">用户没有权限查看一个或多个函数可以返回的类。</span><span class="sxs-lookup"><span data-stu-id="36f55-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="36f55-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="36f55-155">0x80041001</span></span> | <span data-ttu-id="36f55-156">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="36f55-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="36f55-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="36f55-157">0x80041008</span></span> | <span data-ttu-id="36f55-158">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="36f55-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="36f55-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="36f55-159">0x80041017</span></span> | <span data-ttu-id="36f55-160">查询必须语法错误。</span><span class="sxs-lookup"><span data-stu-id="36f55-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="36f55-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="36f55-161">0x80041018</span></span> | <span data-ttu-id="36f55-162">不支持请求的查询语言。</span><span class="sxs-lookup"><span data-stu-id="36f55-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="36f55-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="36f55-163">0x8004106c</span></span> | <span data-ttu-id="36f55-164">查询太过复杂。</span><span class="sxs-lookup"><span data-stu-id="36f55-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="36f55-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="36f55-165">0x80041006</span></span> | <span data-ttu-id="36f55-166">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="36f55-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="36f55-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="36f55-167">0x80041033</span></span> | <span data-ttu-id="36f55-168">WMI 时可能已停止和重新启动。</span><span class="sxs-lookup"><span data-stu-id="36f55-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="36f55-169">调用[ConnectServerWmi](connectserverwmi.md)试。</span><span class="sxs-lookup"><span data-stu-id="36f55-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="36f55-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="36f55-170">0x80041015</span></span> | <span data-ttu-id="36f55-171">之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。</span><span class="sxs-lookup"><span data-stu-id="36f55-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="36f55-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="36f55-172">0x80041002</span></span> | <span data-ttu-id="36f55-173">查询指定不存在的类。</span><span class="sxs-lookup"><span data-stu-id="36f55-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="36f55-174">0</span><span class="sxs-lookup"><span data-stu-id="36f55-174">0</span></span> | <span data-ttu-id="36f55-175">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="36f55-175">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="36f55-176">备注</span><span class="sxs-lookup"><span data-stu-id="36f55-176">Remarks</span></span>

<span data-ttu-id="36f55-177">此函数包装对的调用[IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="36f55-177">This function wraps a call to the [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="36f55-178">此函数处理中指定的查询`strQuery`参数和创建一个通过其调用方可以访问查询结果的枚举器。</span><span class="sxs-lookup"><span data-stu-id="36f55-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="36f55-179">枚举器是一个指向[IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx)接口; 查询结果是通过提供的类对象的实例[IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="36f55-179">The enumerator is a pointer to an [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) interface; the query results are instances of class objects made available through the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) interface.</span></span>

<span data-ttu-id="36f55-180">对于数没有限制`AND`和`OR`关键字可以在 WQL 查询中使用。</span><span class="sxs-lookup"><span data-stu-id="36f55-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="36f55-181">大量复杂的查询中使用的 WQL 关键字可能会导致 WMI 返回`WBEM_E_QUOTA_VIOLATION`（或 0x8004106c） 错误代码为`HRESULT`值。</span><span class="sxs-lookup"><span data-stu-id="36f55-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="36f55-182">WQL 关键字的限制取决于如何复杂查询是。</span><span class="sxs-lookup"><span data-stu-id="36f55-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="36f55-183">如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="36f55-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="36f55-184">要求</span><span class="sxs-lookup"><span data-stu-id="36f55-184">Requirements</span></span>  
 <span data-ttu-id="36f55-185">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36f55-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36f55-186">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="36f55-186">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="36f55-187">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="36f55-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f55-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="36f55-188">See also</span></span>  
[<span data-ttu-id="36f55-189">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="36f55-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
