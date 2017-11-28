---
title: "AssemblyOptions 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyOptions
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccbbcabd3fbb372322ca6334f6ab6db4fdafc2f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions 枚举
枚举的程序集选项。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>字段  
  
|字段|描述|  
|-----------|-----------------|  
|optAssemTitle|字符串 – 表示程序集的标题。|  
|optAssemDescription|字符串--包含程序集描述。|  
|optAssemConfig|字符串--包含程序集配置。|  
|optAssemOS|字符串的编码为:"dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion"。|  
|optAssemProcessor|ULONG|  
|optAssemLocale|字符串--包含程序集的区域设置。|  
|optAssemVersion|字符串的编码为:"Major.Minor.Build.Revision"。|  
|optAssemCompany|字符串--包含公司。|  
|optAssemProduct|字符串--包含产品名称。|  
|optAssemProductVersion|字符串 (也称为 InformationalVersion)。|  
|optAssemCopyright|字符串--包含的版权信息。|  
|optAssemTrademark|字符串--包含商标信息。|  
|optAssemKeyFile|字符串 （文件名）。|  
|optAssemKeyName|字符串 （密钥名称）。|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool （也称为 DelaySign）。|  
|optAssemFileVersion|字符串的编码为"Major.Minor.Build.Revision"-ProductVersion 相同。|  
|optAssemSatelliteVer|编码的字符串的"Major.Minor.Build.Revision"形式。|  
|optLastAssemOption|元素数的计数器。|  
  
## <a name="requirements"></a>要求  
 **标头：** alink.h  
  
 **库**: alink.dll  
  
## <a name="see-also"></a>另请参阅  
 [Al.exe（程序集链接器）](../../../../docs/framework/tools/al-exe-assembly-linker.md)
