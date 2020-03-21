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
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175221"
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
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`dwOSPlatformId`|由微软 Windows 平台函数`GetVersionEx`定义的标识符值之一。 支持以下值：<br /><br /> - VER_PLATFORM_WIN32s，或 0x0000，以指定微软 Windows 3.1。<br />- VER_PLATFORM_WIN32_WINDOWS，或 0x0001，以指定 Windows 95、Windows 98 或它们产生的操作系统。<br />- VER_PLATFORM_WIN32_NT，或 0x0002，以指定 Windows NT 或操作系统从它下降。|  
|`dwOSMajorVersion`|操作系统主版本，或用于指示任何版本的 NULL 值。|  
|`dwOSMinorVersion`|操作系统次要版本，或用于指示任何版本的 NULL 值。|  
  
## <a name="remarks"></a>备注  
 `OSINFO`基于调用微软`OSVERSIONINFOEX`Windows 平台功能`GetVersionEx`时使用的结构。 此结构由 ASSEMBLYMETADATA 结构用于指示其操作系统支持。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据结构](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
