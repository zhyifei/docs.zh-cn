---
title: CorFileMapping 枚举
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c8864aa604b0483130eac5aa0d7c0640abbac99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443718"
---
# <a name="corfilemapping-enumeration"></a>CorFileMapping 枚举
包含值，用于描述从调用返回的文件映射的类型[imetadatainfo::](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`fmFlat`|作为数据文件映射文件。 也就是说，`SEC_IMAGE`标志中未传递给 Microsoft Win32`CreateFileMapping`函数。|  
|`fmExecutableImage`|该文件为映射，则执行、 通过使用`LoadLibrary`函数或`CreateFileMapping`起作用`SEC_IMAGE`标志。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [GetFileMapping 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
