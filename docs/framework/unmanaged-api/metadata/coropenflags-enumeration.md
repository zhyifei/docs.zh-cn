---
title: "CorOpenFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorOpenFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorOpenFlags
helpviewer_keywords: CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4447f648277576169c9004d1880283728639c8f3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="coropenflags-enumeration"></a>CorOpenFlags 枚举
包含一些标志值，用于控制打开清单文件时的元数据行为。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`ofRead`|指示该文件应在只读状态下打开。|  
|`ofWrite`|指示该文件应在可写入状态下打开。<br /><br /> 如果在打开 .winmd 文件时使用 `ofWrite` 标志，则你还应该传递 `ofNoTransform` 标志。|  
|`ofReadWriteMask`|读写操作的掩码。|  
|`ofCopyMemory`|指示应将该文件读入内存。 元数据应保持自己的副本。|  
|`ofCacheImage`|已过时。 将忽略此标志。|  
|`ofManifestMetadata`|已过时。 将忽略此标志。|  
|`ofReadOnly`|指示应打开文件进行读取，并且调用`QueryInterface`为[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)无法进行。|  
|`ofTakeOwnership`|指示已分配内存的使用调用[CoTaskMemAlloc](http://msdn.microsoft.com/library/c4cb588d-9482-4f90-a92e-75b604540d5c)和由元数据会被释放。|  
|`ofNoTypeLib`|已过时。 将忽略此标志。|  
|`ofNoTransform`|指示应该禁用 .winmd 文件的自动转换。 也就是说，应该禁用从 Windows 运行时类型到 .NET Framework 类型的投影。 有关详细信息，请参阅[.NET 和 Windows 运行时的内涵](http://msdn.microsoft.com/magazine/jj651569.aspx)。|  
|`ofReserved1`|保留以供内部使用。|  
|`ofReserved2`|保留以供内部使用。|  
|`ofReserved`|保留以供内部使用。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
