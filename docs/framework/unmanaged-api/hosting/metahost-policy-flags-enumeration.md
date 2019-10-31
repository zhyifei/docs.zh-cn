---
title: METAHOST_POLICY_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
ms.openlocfilehash: a028d2a8116de4df79f662ee8b2768e6e070428a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141396"
---
# <a name="metahost_policy_flags-enumeration"></a><span data-ttu-id="fa6de-102">METAHOST_POLICY_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="fa6de-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="fa6de-103">提供大多数运行时主机通用的绑定策略。</span><span class="sxs-lookup"><span data-stu-id="fa6de-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="fa6de-104">此枚举由[ICLRMetaHostPolicy：： GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法使用。</span><span class="sxs-lookup"><span data-stu-id="fa6de-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6de-105">语法</span><span class="sxs-lookup"><span data-stu-id="fa6de-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="fa6de-106">Members</span><span class="sxs-lookup"><span data-stu-id="fa6de-106">Members</span></span>  
  
|<span data-ttu-id="fa6de-107">成员</span><span class="sxs-lookup"><span data-stu-id="fa6de-107">Member</span></span>|<span data-ttu-id="fa6de-108">描述</span><span class="sxs-lookup"><span data-stu-id="fa6de-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="fa6de-109">定义高兼容性策略，该策略不考虑加载到当前进程中的任何公共语言运行时（CLR）。</span><span class="sxs-lookup"><span data-stu-id="fa6de-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="fa6de-110">相反，它仅考虑已安装的 Clr 和组件的首选项，派生自程序集文件本身、声明的生成版本或配置文件。</span><span class="sxs-lookup"><span data-stu-id="fa6de-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="fa6de-111">基于 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\的内容找不到完全匹配时，将升级策略应用到版本绑定结果。NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="fa6de-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="fa6de-112">这与[RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)的效果相同。</span><span class="sxs-lookup"><span data-stu-id="fa6de-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="fa6de-113">返回绑定结果，就好像在新进程中启动了提供给调用的图像一样。</span><span class="sxs-lookup"><span data-stu-id="fa6de-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="fa6de-114">目前，`GetRequestedRuntime` 忽略一组可加载的运行时，并与已安装的运行时集绑定。</span><span class="sxs-lookup"><span data-stu-id="fa6de-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="fa6de-115">此标志允许主机在启动时确定 EXE 将绑定到的运行时。</span><span class="sxs-lookup"><span data-stu-id="fa6de-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="fa6de-116">如果 `GetRequestedRuntime` 找不到与输入参数兼容的运行时，则会显示错误对话框。</span><span class="sxs-lookup"><span data-stu-id="fa6de-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="fa6de-117">从 .NET Framework 4.5 开始，此错误对话框可以采用 Windows 功能对话框的形式，该对话框会询问用户是否要启用相应的功能。</span><span class="sxs-lookup"><span data-stu-id="fa6de-117">Beginning with the .NET Framework 4.5, this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="fa6de-118">`GetRequestedRuntime` 使用进程图像（以及任何相应的配置文件）作为绑定过程的附加输入。</span><span class="sxs-lookup"><span data-stu-id="fa6de-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="fa6de-119">默认情况下，在确定运行时绑定到时，`GetRequestedRuntime` 不会回退到进程映像路径（通常是用于启动进程的 EXE）。</span><span class="sxs-lookup"><span data-stu-id="fa6de-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="fa6de-120">如果配置文件中没有可用的信息，`GetRequestedRuntime` 必须检查是否安装了相应的 SKU。</span><span class="sxs-lookup"><span data-stu-id="fa6de-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="fa6de-121">这允许不具有配置文件的应用程序在 .NET Framework 的默认安装的较小 Sku 上正常失败。</span><span class="sxs-lookup"><span data-stu-id="fa6de-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="fa6de-122">默认情况下，`GetRequestedRuntime` 不会检查是否安装了相应的 SKU，除非在配置文件 `<supportedRuntime />` 元素中指定 SKU 属性。</span><span class="sxs-lookup"><span data-stu-id="fa6de-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="fa6de-123">`GetRequestedRuntime` 应忽略 SEM_FAILCRITICALERRORS （通过调用[SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242)函数设置），并显示错误对话框。</span><span class="sxs-lookup"><span data-stu-id="fa6de-123">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="fa6de-124">默认情况下，SEM_FAILCRITICALERRORS 禁止显示错误对话框。</span><span class="sxs-lookup"><span data-stu-id="fa6de-124">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="fa6de-125">它可能已被其他进程继承，并且在你的方案中可能不需要此错误。</span><span class="sxs-lookup"><span data-stu-id="fa6de-125">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa6de-126">备注</span><span class="sxs-lookup"><span data-stu-id="fa6de-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa6de-127">要求</span><span class="sxs-lookup"><span data-stu-id="fa6de-127">Requirements</span></span>  
 <span data-ttu-id="fa6de-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa6de-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa6de-129">**标头：** Metahost</span><span class="sxs-lookup"><span data-stu-id="fa6de-129">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="fa6de-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="fa6de-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa6de-131">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa6de-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6de-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa6de-132">See also</span></span>

- [<span data-ttu-id="fa6de-133">承载枚举</span><span class="sxs-lookup"><span data-stu-id="fa6de-133">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="fa6de-134">GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="fa6de-134">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
