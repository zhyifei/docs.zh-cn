---
title: CreateDebuggingInterfaceFromVersion 函数
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176443"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="efca1-102">CreateDebuggingInterfaceFromVersion 函数</span><span class="sxs-lookup"><span data-stu-id="efca1-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="efca1-103">根据指定的版本信息创建[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="efca1-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="efca1-104">此功能在 .NET 框架 4 中已过时。</span><span class="sxs-lookup"><span data-stu-id="efca1-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="efca1-105">相反，要获取通用语言运行时 （CLR） 2.0 的接口，请使用[ICLRRuntimeinfo：getInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)方法，并指定类标识符CLSID_CLRDebuggingLegacy和接口标识符IID_ICorDebug。</span><span class="sxs-lookup"><span data-stu-id="efca1-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="efca1-106">要获取 CLR 4 或更高版本的接口，请调用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数，并指定类标识符CLSID_CLRDebugging和接口标识符IID_ICLRDebugging。</span><span class="sxs-lookup"><span data-stu-id="efca1-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efca1-107">语法</span><span class="sxs-lookup"><span data-stu-id="efca1-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efca1-108">parameters</span><span class="sxs-lookup"><span data-stu-id="efca1-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="efca1-109">[在]`ICorDebug`调试器预期的版本。</span><span class="sxs-lookup"><span data-stu-id="efca1-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="efca1-110">有关有效值，请参阅[CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="efca1-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="efca1-111">[在]与要调试的应用程序或进程关联的通用语言运行时版本。</span><span class="sxs-lookup"><span data-stu-id="efca1-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="efca1-112">有关检索此值的信息，请参阅[获取从进程](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)获取版本或[获取请求运行时版本](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)的方法。</span><span class="sxs-lookup"><span data-stu-id="efca1-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="efca1-113">[出]接收指向`ICorDebug`对象的指针的位置。</span><span class="sxs-lookup"><span data-stu-id="efca1-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efca1-114">返回值</span><span class="sxs-lookup"><span data-stu-id="efca1-114">Return Value</span></span>  
 <span data-ttu-id="efca1-115">此方法返回 WinError.h 文件中定义的标准 COM 错误代码以及以下值。</span><span class="sxs-lookup"><span data-stu-id="efca1-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="efca1-116">返回代码</span><span class="sxs-lookup"><span data-stu-id="efca1-116">Return code</span></span>|<span data-ttu-id="efca1-117">说明</span><span class="sxs-lookup"><span data-stu-id="efca1-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="efca1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="efca1-118">S_OK</span></span>|<span data-ttu-id="efca1-119">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="efca1-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="efca1-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="efca1-120">E_INVALIDARG</span></span>|<span data-ttu-id="efca1-121">`szDebuggeeVersion`或`ppCordb`为 null，或者版本字符串不正确。</span><span class="sxs-lookup"><span data-stu-id="efca1-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efca1-122">备注</span><span class="sxs-lookup"><span data-stu-id="efca1-122">Remarks</span></span>  
 <span data-ttu-id="efca1-123">参数`szDebuggeeVersion`映射到相应的 MSCorDbi.dll 版本。</span><span class="sxs-lookup"><span data-stu-id="efca1-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efca1-124">要求</span><span class="sxs-lookup"><span data-stu-id="efca1-124">Requirements</span></span>  
 <span data-ttu-id="efca1-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efca1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efca1-126">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="efca1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efca1-127">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="efca1-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efca1-128">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efca1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efca1-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efca1-129">See also</span></span>

- [<span data-ttu-id="efca1-130">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="efca1-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
