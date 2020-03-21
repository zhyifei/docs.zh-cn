---
title: CorPinvokeMap 枚举
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
ms.openlocfilehash: 8216dc3030b18428ab52fbf8385d392f81057aa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176144"
---
# <a name="corpinvokemap-enumeration"></a>CorPinvokeMap 枚举
指定 PInvoke 调用的选项。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`pmNoMangle`|使用指定的每个成员名称。|  
|`pmCharSetMask`|保留。|  
|`pmCharSetNotSpec`|保留。|  
|`pmCharSetAnsi`|以多字节字符串的形式封送字符串。|  
|`pmCharSetUnicode`|以 Unicode 2 字节字符的形式封送字符串。|  
|`pmCharSetAuto`|针对目标操作系统适当地自动封送字符串。 默认值为 Windows NT、Windows 2000、Windows XP 和 Windows Server 2003 系列上的 Unicode;默认值为 Windows 98 上的 ANSI 和 Windows Me。|  
|`pmBestFitUseAssem`|保留。|  
|`pmBestFitEnabled`|对 ANSI 字符集中缺少完全匹配的 Unicode 字符执行最佳映射。|  
|`pmBestFitDisabled`|不要执行最适合的 Unicode 字符映射。 在这种情况下，所有不可映射的字符将替换为"？"。|  
|`pmBestFitMask`|保留。|  
|`pmThrowOnUnmappableCharUseAssem`|保留。|  
|`pmThrowOnUnmappableCharEnabled`|当互通封送器遇到不可映射的字符时引发异常。|  
|`pmThrowOnUnmappableCharDisabled`|当互通封送器遇到不可映射的字符时，不要引发异常。|  
|`pmThrowOnUnmappableCharMask`|保留|  
|`pmSupportsLastError`|允许被调用人调用 Win32`SetLastError`函数，然后再从属性化方法返回。|  
|`pmCallConvMask`|保留|  
|`pmCallConvWinapi`|使用默认平台调用约定。 例如，在 Windows 上，`StdCall`默认值为 ，在 Windows `Cdecl`CE .NET 上，默认值为 。|  
|`pmCallConvCdecl`|使用`Cdecl`调用约定。 在这种情况下，调用方清理堆栈。 这允许调用函数（`varargs`即接受可变数量的参数的函数）。|  
|`pmCallConvStdcall`|使用`StdCall`调用约定。 在这种情况下，被叫人清理堆栈。 这是使用平台 invoke 调用非托管函数的默认约定。|  
|`pmCallConvThiscall`|使用`ThisCall`调用约定。 在这种情况下，第一个参数是指针，`this`并存储在寄存器 ECX 中。 其他参数被推送到堆栈上。 调用`ThisCall`约定用于调用从非托管 DLL 导出的类上的方法。|  
|`pmCallConvFastcall`|保留。|  
|`pmMaxValue`|保留。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫德  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
