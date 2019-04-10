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
ms.openlocfilehash: a3056836d289383161f9fa538c3c6349f88b6ba6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175612"
---
# <a name="corfilemapping-enumeration"></a>CorFileMapping 枚举
包含描述从调用返回的文件映射的类型的值[imetadatainfo:: Getfilemapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)方法。  
  
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
|`fmFlat`|为数据文件映射文件。 即`SEC_IMAGE`标志未传递到 Microsoft Win32`CreateFileMapping`函数。|  
|`fmExecutableImage`|对于执行，通过使用映射文件`LoadLibrary`函数或`CreateFileMapping`函数与`SEC_IMAGE`标志。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [元数据枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [GetFileMapping 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
