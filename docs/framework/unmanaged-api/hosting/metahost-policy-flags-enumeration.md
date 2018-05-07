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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f980fb1336adaf43091e41b9e42ea008b00c033f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="metahostpolicyflags-enumeration"></a>METAHOST_POLICY_FLAGS 枚举
提供共有的大多数运行时主机的绑定策略。 此枚举由[iclrmetahostpolicy:: Getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
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
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|定义了高兼容性策略，它不考虑任何公共语言运行时 (CLR) 加载到当前进程。 相反，它认为已安装的 Clr 和首选项的组件，如派生自该组件文件本身、 声明生成针对版本或配置文件。|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|升级策略适用于版本的绑定结果，未找到完全匹配，根据 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft 的内容时\\。NETFramework\Policy\Upgrades。 这具有相同的效果[RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)。|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|绑定结果返回如同在新进程中启动为调用提供的映像。 目前，`GetRequestedRuntime`忽略的一套可加载运行时并根据安装的运行时绑定。 此标志将允许宿主确定 EXE 将绑定到它启动时的运行时。|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|如果显示错误对话框`GetRequestedRuntime`找不到的运行时兼容的输入参数。 开头[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，此错误对话框中可以采用以下形式的 Windows 功能对话框，询问是否用户想要启用适当的功能。|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` 使用作为附加输入到绑定进程的进程映像 （和任何相应的配置文件）。 默认情况下，`GetRequestedRuntime`不会回退到进程映像路径 (通常情况下，用于启动进程的 EXE) 在确定要将绑定到的运行时。|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` 必须检查时没有的信息可在配置文件中是否安装了适当的 SKU。 这允许应用程序不具有配置文件来比默认安装的.NET framework 的较小 sku 优雅地失败。 默认情况下，`GetRequestedRuntime`不会检查是否已安装了适当的 SKU，除非在配置文件中指定 SKU 属性`<supportedRuntime />`元素。|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` 必须检查时没有的信息可在配置文件中是否安装了适当的 SKU。 这允许应用程序不具有配置文件来比默认安装的.NET framework 的较小 sku 优雅地失败。 默认情况下，`GetRequestedRuntime`不会检查是否已安装了适当的 SKU，除非在配置文件中指定 SKU 属性`<supportedRuntime />`元素。|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` 应忽略 SEM_FAILCRITICALERRORS (通过调用设有[SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242)函数)，并显示错误对话框。 默认情况下，SEM_FAILCRITICALERRORS 会禁止显示错误对话框。 它可能已被继承从另一个进程，并可能在你的方案中不希望无提示的错误。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Metahost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [GetRequestedRuntime 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
