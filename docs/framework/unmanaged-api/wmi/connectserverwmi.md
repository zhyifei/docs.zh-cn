---
title: "ConnectServerWmi 函数 （非托管 API 参考）"
description: "ConnectServerWmi 函数使用 DCOM 创建与 WMI 命名空间的连接。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ConnectServerWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ConnectServerWmi
helpviewer_keywords: ConnectServerWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b51050bce4603ebcfe99fb38d66e54683c677293
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="bf594-103">ConnectServerWmi 函数</span><span class="sxs-lookup"><span data-stu-id="bf594-103">ConnectServerWmi function</span></span>
<span data-ttu-id="bf594-104">指定计算机上创建的 WMI 命名空间通过 DCOM 的连接。</span><span class="sxs-lookup"><span data-stu-id="bf594-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bf594-105">语法</span><span class="sxs-lookup"><span data-stu-id="bf594-105">Syntax</span></span>  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a><span data-ttu-id="bf594-106">参数</span><span class="sxs-lookup"><span data-stu-id="bf594-106">Parameters</span></span>

<span data-ttu-id="bf594-107">`strNetworkResource`[in]指针到有效`BSTR`包含正确的 WMI 命名空间的对象路径。</span><span class="sxs-lookup"><span data-stu-id="bf594-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="bf594-108">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="bf594-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="bf594-109">`strUser`[in]指向一个有效的指针`BSTR`包含的用户名称。</span><span class="sxs-lookup"><span data-stu-id="bf594-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="bf594-110">A`null`值指示当前的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="bf594-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="bf594-111">如果用户是从不同的域与当前`strUser`还可以包含反斜杠分隔的域和用户名称。</span><span class="sxs-lookup"><span data-stu-id="bf594-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="bf594-112">`strUser`此外可以将在用户主体名称 (UPN) 设置格式，作为 suhc  *userName@domainName* 。</span><span class="sxs-lookup"><span data-stu-id="bf594-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="bf594-113">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="bf594-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="bf594-114">`strPassword`[in]指向一个有效的指针`BSTR`包含的密码。</span><span class="sxs-lookup"><span data-stu-id="bf594-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="bf594-115">A`null`指示当前的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="bf594-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="bf594-116">空字符串 ("") 指示有效长度为零的密码。</span><span class="sxs-lookup"><span data-stu-id="bf594-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="bf594-117">`strLocale`[in]指向一个有效的指针`BSTR`，该值指示用于信息检索正确的区域设置。</span><span class="sxs-lookup"><span data-stu-id="bf594-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="bf594-118">对于 Microsoft 区域设置标识符，字符串的格式是"MS\_*xxx*"，其中*xxx*以十六进制形式，该值指示的区域设置标识符 (LCID) 是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="bf594-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="bf594-119">如果指定了无效的区域设置，该方法返回`WBEM_E_INVALID_PARAMETER`在 Windows 7，其中服务器的默认区域设置改为使用上除外。</span><span class="sxs-lookup"><span data-stu-id="bf594-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="bf594-120">如果使用 null1，当前区域设置。</span><span class="sxs-lookup"><span data-stu-id="bf594-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="bf594-121">`lSecurityFlags`[in]要传递给标志`ConnectServerWmi`方法。</span><span class="sxs-lookup"><span data-stu-id="bf594-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="bf594-122">为零 (0)，此参数值将导致调用`ConnectServerWmi`返回仅后建立到服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="bf594-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="bf594-123">这可能导致应用程序未响应无限期地如果服务器将断开。</span><span class="sxs-lookup"><span data-stu-id="bf594-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="bf594-124">其他有效值为：</span><span class="sxs-lookup"><span data-stu-id="bf594-124">The other valid values are:</span></span>

| <span data-ttu-id="bf594-125">返回的常量</span><span class="sxs-lookup"><span data-stu-id="bf594-125">Constant</span></span>  | <span data-ttu-id="bf594-126">值</span><span class="sxs-lookup"><span data-stu-id="bf594-126">Value</span></span>  | <span data-ttu-id="bf594-127">描述</span><span class="sxs-lookup"><span data-stu-id="bf594-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="bf594-128">0x40</span><span class="sxs-lookup"><span data-stu-id="bf594-128">0x40</span></span> | <span data-ttu-id="bf594-129">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="bf594-129">Reserved for internal use.</span></span> <span data-ttu-id="bf594-130">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="bf594-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="bf594-131">0x80</span><span class="sxs-lookup"><span data-stu-id="bf594-131">0x80</span></span> | <span data-ttu-id="bf594-132">`ConnectServerWmi`返回在两分钟或更短。</span><span class="sxs-lookup"><span data-stu-id="bf594-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="bf594-133">`strAuthority`[in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="bf594-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="bf594-134">可以有下列值：</span><span class="sxs-lookup"><span data-stu-id="bf594-134">It can have the following values:</span></span>

| <span data-ttu-id="bf594-135">值</span><span class="sxs-lookup"><span data-stu-id="bf594-135">Value</span></span> | <span data-ttu-id="bf594-136">描述</span><span class="sxs-lookup"><span data-stu-id="bf594-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="bf594-137">空白</span><span class="sxs-lookup"><span data-stu-id="bf594-137">blank</span></span> | <span data-ttu-id="bf594-138">使用 NTLM 身份验证，并使用当前用户的 NTLM 该域。</span><span class="sxs-lookup"><span data-stu-id="bf594-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="bf594-139">如果`strUser`指定的域 （推荐位置），它必须不此处指定。</span><span class="sxs-lookup"><span data-stu-id="bf594-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="bf594-140">该函数将返回`WBEM_E_INVALID_PARAMETER`如果这两个参数中指定的域。</span><span class="sxs-lookup"><span data-stu-id="bf594-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="bf594-141">Kerberos:*主体名称*</span><span class="sxs-lookup"><span data-stu-id="bf594-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="bf594-142">使用 Kerberos 身份验证，并且此参数包含 Kerberos 主体名称。</span><span class="sxs-lookup"><span data-stu-id="bf594-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="bf594-143">NTLMDOMAIN:*域名*</span><span class="sxs-lookup"><span data-stu-id="bf594-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="bf594-144">使用 NT LAN 管理器身份验证，并且此参数包含的 NTLM 域名。</span><span class="sxs-lookup"><span data-stu-id="bf594-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="bf594-145">[in]通常，此参数是`null`。</span><span class="sxs-lookup"><span data-stu-id="bf594-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="bf594-146">否则，它是一个指向[IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx)所需的一个或多个动态类提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="bf594-146">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="bf594-147">[out]当函数返回时，接收一个指针，到[IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx)对象绑定到指定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="bf594-147">[out] When the function returns, receives a pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object bound to the specified namespace.</span></span> <span data-ttu-id="bf594-148">它被设置为指向`null`时出错。</span><span class="sxs-lookup"><span data-stu-id="bf594-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="bf594-149">[in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="bf594-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="bf594-150">[in]授权级别中。</span><span class="sxs-lookup"><span data-stu-id="bf594-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="bf594-151">返回值</span><span class="sxs-lookup"><span data-stu-id="bf594-151">Return value</span></span>

<span data-ttu-id="bf594-152">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="bf594-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bf594-153">返回的常量</span><span class="sxs-lookup"><span data-stu-id="bf594-153">Constant</span></span>  |<span data-ttu-id="bf594-154">值</span><span class="sxs-lookup"><span data-stu-id="bf594-154">Value</span></span>  |<span data-ttu-id="bf594-155">描述</span><span class="sxs-lookup"><span data-stu-id="bf594-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="bf594-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="bf594-156">0x80041001</span></span> | <span data-ttu-id="bf594-157">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="bf594-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bf594-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bf594-158">0x80041008</span></span> | <span data-ttu-id="bf594-159">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="bf594-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bf594-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bf594-160">0x80041006</span></span> | <span data-ttu-id="bf594-161">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="bf594-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="bf594-162">0</span><span class="sxs-lookup"><span data-stu-id="bf594-162">0</span></span> | <span data-ttu-id="bf594-163">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="bf594-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bf594-164">备注</span><span class="sxs-lookup"><span data-stu-id="bf594-164">Remarks</span></span>

<span data-ttu-id="bf594-165">此函数包装对的调用[IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="bf594-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="bf594-166">有关对默认命名空间，本地访问`strNetworkResource`可以是简单对象路径:"根 \ 默认"或"\\.\root\default"。</span><span class="sxs-lookup"><span data-stu-id="bf594-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="bf594-167">用于访问远程计算机上的默认命名空间使用 COM 或 Microsoft 兼容的网络，包含计算机名称:"\\myserver\root\default"。</span><span class="sxs-lookup"><span data-stu-id="bf594-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="bf594-168">计算机名称也可以是 DNS 名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="bf594-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="bf594-169">`ConnectServerWmi`函数还可以连接运行 IPv6 的计算机使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="bf594-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="bf594-170">`strUser`不能为空字符串。</span><span class="sxs-lookup"><span data-stu-id="bf594-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="bf594-171">如果在指定了域`strAuthority`，它必须不还会包含在`strUser`，或该函数将返回`WBEM_E_INVALID_PARAMETER`。</span><span class="sxs-lookup"><span data-stu-id="bf594-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="bf594-172">要求</span><span class="sxs-lookup"><span data-stu-id="bf594-172">Requirements</span></span>  
 <span data-ttu-id="bf594-173">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf594-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf594-174">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bf594-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bf594-175">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bf594-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf594-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf594-176">See also</span></span>  
[<span data-ttu-id="bf594-177">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="bf594-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
