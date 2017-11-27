---
title: "CorPinvokeMap 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: CorPinvokeMap
helpviewer_keywords: CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c6e1a49d18cde768884ab3d92eaa6593e2955c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corpinvokemap-enumeration"></a>CorPinvokeMap 枚举
指定为 PInvoke 调用的选项。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
|成员|描述|  
|------------|-----------------|  
|`pmNoMangle`|使用指定的每个成员名称。|  
|`pmCharSetMask`|保留。|  
|`pmCharSetNotSpec`|保留。|  
|`pmCharSetAnsi`|以多字节字符串的形式封送字符串。|  
|`pmCharSetUnicode`|以 Unicode 2 字节字符的形式封送字符串。|  
|`pmCharSetAuto`|针对目标操作系统适当地自动封送字符串。 默认值是 Windows NT、 Windows 2000、 Windows XP 和 Windows Server 2003 系列中; 上的为 Unicode默认值是 Windows 98 和 Windows me 上的为 ANSI|  
|`pmBestFitUseAssem`|保留。|  
|`pmBestFitEnabled`|执行最佳的映射缺少完全匹配 ANSI 字符集中的 Unicode 字符。|  
|`pmBestFitDisabled`|不执行 Unicode 字符的最佳的的映射。 在这种情况下，所有无法映射的字符将替换为？。|  
|`pmBestFitMask`|保留。|  
|`pmThrowOnUnmappableCharUseAssem`|保留。|  
|`pmThrowOnUnmappableCharEnabled`|当互操作封送处理程序遇到无法映射的字符，则引发异常。|  
|`pmThrowOnUnmappableCharDisabled`|当互操作封送处理程序遇到无法映射的字符，则不引发异常。|  
|`pmThrowOnUnmappableCharMask`|保留|  
|`pmSupportsLastError`|允许被调用方调用 Win32`SetLastError`从特性化方法返回之前的函数。|  
|`pmCallConvMask`|保留|  
|`pmCallConvWinapi`|使用默认平台调用约定。 例如，在 Windows 上默认值是`StdCall`和 Windows CE.NET 很`Cdecl`。|  
|`pmCallConvCdecl`|使用`Cdecl`调用约定。 在这种情况下，调用方将清理堆栈。 这使调用函数使用`varargs`（即，接受可变数目的参数的函数）。|  
|`pmCallConvStdcall`|使用`StdCall`调用约定。 在这种情况下，被调用方将清理堆栈。 这是使用平台 invoke 调用非托管函数的默认约定。|  
|`pmCallConvThiscall`|使用`ThisCall`调用约定。 在这种情况下，第一个参数是`this`指针和存储在 ECX 寄存器。 其他参数被推送到堆栈上。 `ThisCall`调用约定用于调用从非托管 DLL 中导出的类上的方法。|  
|`pmCallConvFastcall`|保留。|  
|`pmMaxValue`|保留。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [元数据枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
