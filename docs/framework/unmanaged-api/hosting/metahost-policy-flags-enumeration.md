---
title: "METAHOST_POLICY_FLAGS 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: METAHOST_POLICY_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: METAHOST_POLICY_FLAGS
helpviewer_keywords: METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80abed08cc7659d4218dce445be81481bb5a665b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="6fafe-102">METAHOST_POLICY_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="6fafe-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="6fafe-103">提供共有的大多数运行时主机的绑定策略。</span><span class="sxs-lookup"><span data-stu-id="6fafe-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="6fafe-104">此枚举由[iclrmetahostpolicy:: Getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6fafe-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fafe-105">语法</span><span class="sxs-lookup"><span data-stu-id="6fafe-105">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6fafe-106">成员</span><span class="sxs-lookup"><span data-stu-id="6fafe-106">Members</span></span>  
  
|<span data-ttu-id="6fafe-107">成员</span><span class="sxs-lookup"><span data-stu-id="6fafe-107">Member</span></span>|<span data-ttu-id="6fafe-108">描述</span><span class="sxs-lookup"><span data-stu-id="6fafe-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="6fafe-109">定义了高兼容性策略，它不考虑任何公共语言运行时 (CLR) 加载到当前进程。</span><span class="sxs-lookup"><span data-stu-id="6fafe-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="6fafe-110">相反，它认为已安装的 Clr 和首选项的组件，如派生自该组件文件本身、 声明生成针对版本或配置文件。</span><span class="sxs-lookup"><span data-stu-id="6fafe-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="6fafe-111">升级策略适用于版本的绑定结果，未找到完全匹配，根据 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft 的内容时\\。NETFramework\Policy\Upgrades。</span><span class="sxs-lookup"><span data-stu-id="6fafe-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="6fafe-112">这具有相同的效果[RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="6fafe-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="6fafe-113">绑定结果返回如同在新进程中启动为调用提供的映像。</span><span class="sxs-lookup"><span data-stu-id="6fafe-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="6fafe-114">目前，`GetRequestedRuntime`忽略的一套可加载运行时并根据安装的运行时绑定。</span><span class="sxs-lookup"><span data-stu-id="6fafe-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="6fafe-115">此标志将允许宿主确定 EXE 将绑定到它启动时的运行时。</span><span class="sxs-lookup"><span data-stu-id="6fafe-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="6fafe-116">如果显示错误对话框`GetRequestedRuntime`找不到的运行时兼容的输入参数。</span><span class="sxs-lookup"><span data-stu-id="6fafe-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="6fafe-117">开头[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，此错误对话框中可以采用以下形式的 Windows 功能对话框，询问是否用户想要启用适当的功能。</span><span class="sxs-lookup"><span data-stu-id="6fafe-117">Beginning with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="6fafe-118">`GetRequestedRuntime`使用作为附加输入到绑定进程的进程映像 （和任何相应的配置文件）。</span><span class="sxs-lookup"><span data-stu-id="6fafe-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="6fafe-119">默认情况下，`GetRequestedRuntime`不会回退到进程映像路径 (通常情况下，用于启动进程的 EXE) 在确定要将绑定到的运行时。</span><span class="sxs-lookup"><span data-stu-id="6fafe-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="6fafe-120">`GetRequestedRuntime`必须检查时没有的信息可在配置文件中是否安装了适当的 SKU。</span><span class="sxs-lookup"><span data-stu-id="6fafe-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="6fafe-121">这允许应用程序不具有配置文件来比默认安装的.NET framework 的较小 sku 优雅地失败。</span><span class="sxs-lookup"><span data-stu-id="6fafe-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="6fafe-122">默认情况下，`GetRequestedRuntime`不会检查是否已安装了适当的 SKU，除非在配置文件中指定 SKU 属性`<supportedRuntime />`元素。</span><span class="sxs-lookup"><span data-stu-id="6fafe-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="6fafe-123">`GetRequestedRuntime`必须检查时没有的信息可在配置文件中是否安装了适当的 SKU。</span><span class="sxs-lookup"><span data-stu-id="6fafe-123">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="6fafe-124">这允许应用程序不具有配置文件来比默认安装的.NET framework 的较小 sku 优雅地失败。</span><span class="sxs-lookup"><span data-stu-id="6fafe-124">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="6fafe-125">默认情况下，`GetRequestedRuntime`不会检查是否已安装了适当的 SKU，除非在配置文件中指定 SKU 属性`<supportedRuntime />`元素。</span><span class="sxs-lookup"><span data-stu-id="6fafe-125">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="6fafe-126">`GetRequestedRuntime`应忽略 SEM_FAILCRITICALERRORS (通过调用设有[SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242)函数)，并显示错误对话框。</span><span class="sxs-lookup"><span data-stu-id="6fafe-126">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="6fafe-127">默认情况下，SEM_FAILCRITICALERRORS 会禁止显示错误对话框。</span><span class="sxs-lookup"><span data-stu-id="6fafe-127">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="6fafe-128">它可能已被继承从另一个进程，并可能在你的方案中不希望无提示的错误。</span><span class="sxs-lookup"><span data-stu-id="6fafe-128">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fafe-129">备注</span><span class="sxs-lookup"><span data-stu-id="6fafe-129">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fafe-130">惠?</span><span class="sxs-lookup"><span data-stu-id="6fafe-130">Requirements</span></span>  
 <span data-ttu-id="6fafe-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6fafe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fafe-132">**标头：** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="6fafe-132">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="6fafe-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6fafe-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fafe-134">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fafe-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fafe-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fafe-135">See Also</span></span>  
 [<span data-ttu-id="6fafe-136">承载枚举</span><span class="sxs-lookup"><span data-stu-id="6fafe-136">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="6fafe-137">GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="6fafe-137">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
