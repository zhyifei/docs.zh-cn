---
title: OSINFO 结构
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: d66e9bc3a027610d917e15dc9769b92ea1c5fb71
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345605"
---
# <a name="osinfo-structure"></a>OSINFO 结构
包含有关程序集或模块的操作系统的详细信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`dwOSPlatformId`|`GetVersionEx`Microsoft Windows 平台函数定义的标识符值之一。 支持以下值：<br /><br /> -VER_PLATFORM_WIN32s 或0x0000，用于指定 Microsoft Windows 3.1。<br />-VER_PLATFORM_WIN32_WINDOWS 或0x0001，用于指定 Windows 95、Windows 98 或其上的操作系统。<br />-VER_PLATFORM_WIN32_NT 或0x0002，用于指定其上的 Windows NT 或操作系统。|  
|`dwOSMajorVersion`|操作系统主版本，或指示任何版本的 NULL 值。|  
|`dwOSMinorVersion`|操作系统次要版本，或指示任何版本的 NULL 值。|  
  
## <a name="remarks"></a>备注  
 `OSINFO` 基于对 Microsoft Windows 平台功能 `GetVersionEx`的调用中使用的 `OSVERSIONINFOEX` 结构。 ASSEMBLYMETADATA 结构使用此结构来指示其操作系统支持。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据结构](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
