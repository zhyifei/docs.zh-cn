---
title: "CorAssemblyFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorAssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorAssemblyFlags
helpviewer_keywords: CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 67057944705a1cecd1754c3c11da08725c9a93f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corassemblyflags-enumeration"></a>CorAssemblyFlags 枚举
包含一些值，用于描述应用于程序集编译的元数据。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`afPublicKey`|指示程序集引用包含完整的未经哈希的公钥。|  
|`afPA_None`|指示未指定的处理器体系结构。|  
|`afPA_MSIL`|指示处理器体系结构是非特定 （pe32 +）。|  
|`afPA_x86`|指示处理器体系结构是 x86 （pe32 +）。|  
|`afPA_IA64`|指示处理器体系结构为 Itanium （PE32 +）。|  
|`afPA_AMD64`|指示处理器体系结构是 AMD X64 （PE32 +）。|  
|`afPA_ARM`|指示处理器体系结构是 ARM （pe32 +）。|  
|`afPA_NoPlatform`|指示程序集是引用程序集;也就是说，它将应用于任何体系结构，但无法在任何体系结构上运行。 因此，该标志等同于`afPA_Mask`。|  
|`afPA_Specified`|指示应将处理器体系结构标志传播到`AssemblyRef`记录。|  
|`afPA_Mask`|描述的处理器体系结构的掩码。|  
|`afPA_FullMask`|指定包含处理器体系结构说明。|  
|`afPA_Shift`|指示在处理器体系结构标志到和从索引中的 shift 计数。|  
|`afEnableJITcompileTracking`|指示从相应的值<xref:System.Diagnostics.DebuggableAttribute.DebuggingModes>的<xref:System.Diagnostics.DebuggableAttribute>。|  
|`afDisableJITcompileOptimizer`|指示从相应的值<xref:System.Diagnostics.DebuggableAttribute.DebuggingModes>的<xref:System.Diagnostics.DebuggableAttribute>。|  
|`afRetargetable`|指示程序集可以重定向在运行时的程序集从不同的发布者。|  
|`afContentType_Mask`|描述内容的类型掩码。|  
|`afContentType_Default`|指示默认内容类型。|  
|`afContentType_WindowsRuntime`|指示[!INCLUDE[wrt](../../../../includes/wrt-md.md)]内容类型。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [元数据枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
