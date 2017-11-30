---
title: "IMetaDataImport2::GetPEKind 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetPEKind
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9fc963f38a845db67bb5b5d377ecabf9a40c359f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getpekind-method"></a>IMetaDataImport2::GetPEKind 方法
获取一个值，标识可移植可执行 (PE) 中的代码的性质文件，通常是 DLL 或 EXE 文件，在当前元数据范围中定义。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwPEKind`  
 [out]指向的值的指针[CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)描述 PE 文件的枚举。  
  
 `pdwMachine`  
 [out]指向一个值，标识计算机的体系结构的指针。 请参阅下节，了解可能的值。  
  
## <a name="remarks"></a>备注  
 由引用的值`pdwMachine`参数可以为以下项之一。  
  
|值|计算机体系结构|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014C|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0x0200|Intel IPF|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|x64|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [CorPEKind 枚举](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
