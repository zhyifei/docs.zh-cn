---
title: ConnectServerWmi 函数 （非托管 API 参考）
description: ConnectServerWmi 函数使用 DCOM 来创建与 WMI 命名空间的连接。
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 163e61eef8a753b5b6470285e5e3ce63789e25a4
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45587637"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="bbb78-103">ConnectServerWmi 函数</span><span class="sxs-lookup"><span data-stu-id="bbb78-103">ConnectServerWmi function</span></span>
<span data-ttu-id="bbb78-104">通过 DCOM 创建到指定计算机上的 WMI 命名空间的连接。</span><span class="sxs-lookup"><span data-stu-id="bbb78-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bbb78-105">语法</span><span class="sxs-lookup"><span data-stu-id="bbb78-105">Syntax</span></span>  
  
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
## <a name="parameters"></a><span data-ttu-id="bbb78-106">参数</span><span class="sxs-lookup"><span data-stu-id="bbb78-106">Parameters</span></span>

<span data-ttu-id="bbb78-107">`strNetworkResource` [in]指向有效`BSTR`包含正确的 WMI 命名空间的对象路径。</span><span class="sxs-lookup"><span data-stu-id="bbb78-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="bbb78-108">请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="bbb78-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="bbb78-109">`strUser` [in]指向一个有效的指针`BSTR`，其中包含的用户名称。</span><span class="sxs-lookup"><span data-stu-id="bbb78-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="bbb78-110">一个`null`值指示当前的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="bbb78-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="bbb78-111">如果用户是从不同的域与当前`strUser`还可以包含一个反斜杠分隔的域和用户名称。</span><span class="sxs-lookup"><span data-stu-id="bbb78-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="bbb78-112">`strUser` 此外可以为用户主体名称 (UPN) 设置格式，作为 suhc *userName@domainName*。</span><span class="sxs-lookup"><span data-stu-id="bbb78-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="bbb78-113">请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="bbb78-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="bbb78-114">`strPassword` [in]指向一个有效的指针`BSTR`包含的密码。</span><span class="sxs-lookup"><span data-stu-id="bbb78-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="bbb78-115">一个`null`指示当前的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="bbb78-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="bbb78-116">空字符串 ("") 指示有效长度为零的密码。</span><span class="sxs-lookup"><span data-stu-id="bbb78-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="bbb78-117">`strLocale` [in]指向一个有效的指针`BSTR`，该值指示正确的区域设置的信息检索。</span><span class="sxs-lookup"><span data-stu-id="bbb78-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="bbb78-118">对于 Microsoft 区域设置标识符的字符串的格式是"MS\_*xxx*"，其中*xxx*是一个字符串中指示的区域设置标识符 (LCID) 的十六进制格式。</span><span class="sxs-lookup"><span data-stu-id="bbb78-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="bbb78-119">如果指定了无效的区域设置，该方法返回`WBEM_E_INVALID_PARAMETER`上 Windows 7，其中的服务器的默认区域设置改为使用除外。</span><span class="sxs-lookup"><span data-stu-id="bbb78-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="bbb78-120">如果使用 null1，当前区域设置。</span><span class="sxs-lookup"><span data-stu-id="bbb78-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="bbb78-121">`lSecurityFlags` [in]要传递给标志`ConnectServerWmi`方法。</span><span class="sxs-lookup"><span data-stu-id="bbb78-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="bbb78-122">此参数为零 (0) 的值将导致调用`ConnectServerWmi`返回才建立到服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="bbb78-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="bbb78-123">这可能导致应用程序未响应无限期地服务器已中断。</span><span class="sxs-lookup"><span data-stu-id="bbb78-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="bbb78-124">其他有效值为：</span><span class="sxs-lookup"><span data-stu-id="bbb78-124">The other valid values are:</span></span>

| <span data-ttu-id="bbb78-125">返回的常量</span><span class="sxs-lookup"><span data-stu-id="bbb78-125">Constant</span></span>  | <span data-ttu-id="bbb78-126">“值”</span><span class="sxs-lookup"><span data-stu-id="bbb78-126">Value</span></span>  | <span data-ttu-id="bbb78-127">描述</span><span class="sxs-lookup"><span data-stu-id="bbb78-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="bbb78-128">0x40</span><span class="sxs-lookup"><span data-stu-id="bbb78-128">0x40</span></span> | <span data-ttu-id="bbb78-129">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="bbb78-129">Reserved for internal use.</span></span> <span data-ttu-id="bbb78-130">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="bbb78-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="bbb78-131">0x80</span><span class="sxs-lookup"><span data-stu-id="bbb78-131">0x80</span></span> | <span data-ttu-id="bbb78-132">`ConnectServerWmi` 返回在两分钟或更少。</span><span class="sxs-lookup"><span data-stu-id="bbb78-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="bbb78-133">`strAuthority` [in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="bbb78-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="bbb78-134">可以有下列值：</span><span class="sxs-lookup"><span data-stu-id="bbb78-134">It can have the following values:</span></span>

| <span data-ttu-id="bbb78-135">“值”</span><span class="sxs-lookup"><span data-stu-id="bbb78-135">Value</span></span> | <span data-ttu-id="bbb78-136">描述</span><span class="sxs-lookup"><span data-stu-id="bbb78-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="bbb78-137">空白</span><span class="sxs-lookup"><span data-stu-id="bbb78-137">blank</span></span> | <span data-ttu-id="bbb78-138">使用 NTLM 身份验证，并使用当前用户的 NTLM 域。</span><span class="sxs-lookup"><span data-stu-id="bbb78-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="bbb78-139">如果`strUser`指定域 （推荐位置），它必须未在此处指定。</span><span class="sxs-lookup"><span data-stu-id="bbb78-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="bbb78-140">该函数将返回`WBEM_E_INVALID_PARAMETER`如果两个参数中指定的域。</span><span class="sxs-lookup"><span data-stu-id="bbb78-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="bbb78-141">Kerberos:*主体名称*</span><span class="sxs-lookup"><span data-stu-id="bbb78-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="bbb78-142">使用 Kerberos 身份验证，并且此参数包含 Kerberos 主体名称。</span><span class="sxs-lookup"><span data-stu-id="bbb78-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="bbb78-143">NTLMDOMAIN:*域名*</span><span class="sxs-lookup"><span data-stu-id="bbb78-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="bbb78-144">使用 NT LAN Manager 身份验证，并且此参数包含的 NTLM 域名。</span><span class="sxs-lookup"><span data-stu-id="bbb78-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="bbb78-145">[in]通常情况下，此参数才是`null`。</span><span class="sxs-lookup"><span data-stu-id="bbb78-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="bbb78-146">否则，它是一个指向[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)对象所需的一个或多个动态类提供程序。</span><span class="sxs-lookup"><span data-stu-id="bbb78-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="bbb78-147">[out]当函数返回时，接收一个指向[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象绑定到指定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="bbb78-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="bbb78-148">它设置为指向`null`时出现错误。</span><span class="sxs-lookup"><span data-stu-id="bbb78-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="bbb78-149">[in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="bbb78-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="bbb78-150">[in]授权级别。</span><span class="sxs-lookup"><span data-stu-id="bbb78-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="bbb78-151">返回值</span><span class="sxs-lookup"><span data-stu-id="bbb78-151">Return value</span></span>

<span data-ttu-id="bbb78-152">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="bbb78-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bbb78-153">返回的常量</span><span class="sxs-lookup"><span data-stu-id="bbb78-153">Constant</span></span>  |<span data-ttu-id="bbb78-154">“值”</span><span class="sxs-lookup"><span data-stu-id="bbb78-154">Value</span></span>  |<span data-ttu-id="bbb78-155">描述</span><span class="sxs-lookup"><span data-stu-id="bbb78-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="bbb78-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="bbb78-156">0x80041001</span></span> | <span data-ttu-id="bbb78-157">已存在时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="bbb78-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bbb78-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bbb78-158">0x80041008</span></span> | <span data-ttu-id="bbb78-159">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="bbb78-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bbb78-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bbb78-160">0x80041006</span></span> | <span data-ttu-id="bbb78-161">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="bbb78-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="bbb78-162">0</span><span class="sxs-lookup"><span data-stu-id="bbb78-162">0</span></span> | <span data-ttu-id="bbb78-163">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="bbb78-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bbb78-164">备注</span><span class="sxs-lookup"><span data-stu-id="bbb78-164">Remarks</span></span>

<span data-ttu-id="bbb78-165">此函数包装对的调用[IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="bbb78-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="bbb78-166">为本地访问默认命名空间`strNetworkResource`可以是简单的对象路径:"root\default"或"\\.\root\default"。</span><span class="sxs-lookup"><span data-stu-id="bbb78-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="bbb78-167">用于访问远程计算机上的默认命名空间使用 COM 或 Microsoft 兼容的网络，包含计算机名称:"\\myserver\root\default"。</span><span class="sxs-lookup"><span data-stu-id="bbb78-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="bbb78-168">计算机名称也可以是 DNS 名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="bbb78-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="bbb78-169">`ConnectServerWmi`函数还可以连接运行 IPv6 的计算机使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="bbb78-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="bbb78-170">`strUser` 不能为空字符串。</span><span class="sxs-lookup"><span data-stu-id="bbb78-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="bbb78-171">如果在指定了域`strAuthority`，它不还必须包含在`strUser`，或该函数将返回`WBEM_E_INVALID_PARAMETER`。</span><span class="sxs-lookup"><span data-stu-id="bbb78-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="bbb78-172">要求</span><span class="sxs-lookup"><span data-stu-id="bbb78-172">Requirements</span></span>  
 <span data-ttu-id="bbb78-173">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb78-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbb78-174">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bbb78-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bbb78-175">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bbb78-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb78-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbb78-176">See also</span></span>  
[<span data-ttu-id="bbb78-177">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="bbb78-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
