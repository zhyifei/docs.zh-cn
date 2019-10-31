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
# <a name="metahost_policy_flags-enumeration"></a>METAHOST_POLICY_FLAGS 枚举
提供大多数运行时主机通用的绑定策略。 此枚举由[ICLRMetaHostPolicy：： GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法使用。  
  
## <a name="syntax"></a>语法  
  
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
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|定义高兼容性策略，该策略不考虑加载到当前进程中的任何公共语言运行时（CLR）。 相反，它仅考虑已安装的 Clr 和组件的首选项，派生自程序集文件本身、声明的生成版本或配置文件。|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|基于 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\的内容找不到完全匹配时，将升级策略应用到版本绑定结果。NETFramework\Policy\Upgrades. 这与[RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)的效果相同。|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|返回绑定结果，就好像在新进程中启动了提供给调用的图像一样。 目前，`GetRequestedRuntime` 忽略一组可加载的运行时，并与已安装的运行时集绑定。 此标志允许主机在启动时确定 EXE 将绑定到的运行时。|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|如果 `GetRequestedRuntime` 找不到与输入参数兼容的运行时，则会显示错误对话框。 从 .NET Framework 4.5 开始，此错误对话框可以采用 Windows 功能对话框的形式，该对话框会询问用户是否要启用相应的功能。|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` 使用进程图像（以及任何相应的配置文件）作为绑定过程的附加输入。 默认情况下，在确定运行时绑定到时，`GetRequestedRuntime` 不会回退到进程映像路径（通常是用于启动进程的 EXE）。|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|如果配置文件中没有可用的信息，`GetRequestedRuntime` 必须检查是否安装了相应的 SKU。 这允许不具有配置文件的应用程序在 .NET Framework 的默认安装的较小 Sku 上正常失败。 默认情况下，`GetRequestedRuntime` 不会检查是否安装了相应的 SKU，除非在配置文件 `<supportedRuntime />` 元素中指定 SKU 属性。|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` 应忽略 SEM_FAILCRITICALERRORS （通过调用[SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242)函数设置），并显示错误对话框。 默认情况下，SEM_FAILCRITICALERRORS 禁止显示错误对话框。 它可能已被其他进程继承，并且在你的方案中可能不需要此错误。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Metahost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [GetRequestedRuntime 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
