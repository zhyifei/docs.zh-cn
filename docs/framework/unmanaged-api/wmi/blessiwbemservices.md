---
title: "BlessIWbemServices 函数 （非托管 API 参考）"
description: "BlessIWbemServices 函数指示用户凭据是否允许访问 IWbemServices 类。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BlessIWbemServices
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BlessIWbemServices
helpviewer_keywords: BlessIWbemServices function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67431d4272ac1da4d400a5552c61cf464680b502
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="d8016-103">BlessIWbemServices 函数</span><span class="sxs-lookup"><span data-stu-id="d8016-103">BlessIWbemServices function</span></span>
<span data-ttu-id="d8016-104">指示用户凭据是否允许访问指定[IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx)类。</span><span class="sxs-lookup"><span data-stu-id="d8016-104">Indicates whether the user credentials permit access to the specified [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d8016-105">语法</span><span class="sxs-lookup"><span data-stu-id="d8016-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="d8016-106">参数</span><span class="sxs-lookup"><span data-stu-id="d8016-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="d8016-107">[in]指向的指针[IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx)权限是必需的对象。</span><span class="sxs-lookup"><span data-stu-id="d8016-107">[in] A pointer to the [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object for which permissions are required.</span></span>

`strUser`  
<span data-ttu-id="d8016-108">[in]用户名。</span><span class="sxs-lookup"><span data-stu-id="d8016-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="d8016-109">[in]与关联的密码`strUser`。</span><span class="sxs-lookup"><span data-stu-id="d8016-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="d8016-110">`strAuthority`[in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="d8016-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="d8016-111">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="d8016-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="d8016-112">`impLevel`[in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="d8016-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="d8016-113">`authnLevel`[in]授权级别中。</span><span class="sxs-lookup"><span data-stu-id="d8016-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="d8016-114">返回值</span><span class="sxs-lookup"><span data-stu-id="d8016-114">Return value</span></span>

<span data-ttu-id="d8016-115">此函数返回以下值中定义*WinError.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="d8016-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d8016-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="d8016-116">Constant</span></span>  |<span data-ttu-id="d8016-117">值</span><span class="sxs-lookup"><span data-stu-id="d8016-117">Value</span></span>  |<span data-ttu-id="d8016-118">描述</span><span class="sxs-lookup"><span data-stu-id="d8016-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="d8016-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="d8016-119">0x80070057</span></span> | <span data-ttu-id="d8016-120">一个或多个自变量均无效。</span><span class="sxs-lookup"><span data-stu-id="d8016-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="d8016-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="d8016-121">0x80004003</span></span> | <span data-ttu-id="d8016-122">`pIWbemServices` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="d8016-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="d8016-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="d8016-123">0x80000008</span></span> | <span data-ttu-id="d8016-124">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="d8016-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="d8016-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="d8016-125">0x80000002</span></span> | <span data-ttu-id="d8016-126">内存不足是可用于执行该操作。</span><span class="sxs-lookup"><span data-stu-id="d8016-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="d8016-127">0</span><span class="sxs-lookup"><span data-stu-id="d8016-127">0</span></span> | <span data-ttu-id="d8016-128">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="d8016-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="d8016-129">要求</span><span class="sxs-lookup"><span data-stu-id="d8016-129">Requirements</span></span>  
 <span data-ttu-id="d8016-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8016-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8016-131">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d8016-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d8016-132">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d8016-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8016-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8016-133">See also</span></span>  
[<span data-ttu-id="d8016-134">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="d8016-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
