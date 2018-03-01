---
title: "IMetaDataInfo::GetFileMapping 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f974230dc5ddf2a663f05fc06850f49f1de6e773
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping 方法
获取映射的文件和的映射的类型的内存区域。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppvData`  
 [out]指向映射文件的开头的指针。  
  
 `pcbData`  
 [out]映射区域的大小。 如果`pdwMappingType`是`fmFlat`，这是文件的大小。  
  
 `pdwMappingType`  
 [out]A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)值，该值指示的映射的类型。 公共语言运行时 (CLR) 的当前实现始终返回`fmFlat`。 其他值进行保留供将来使用。 但是，您应始终验证返回的值，因为其他值可能在将来版本中启用或服务版本。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|填充所有输出。|  
|`E_INVALIDARG`|作为自变量值传递 NULL。|  
|`COR_E_NOTSUPPORTED`|CLR 实现无法提供有关内存区域的信息。 这可能是由于以下原因：<br /><br /> 元数据范围通过打开`ofWrite`或`ofCopyMemory`标志。<br />元数据范围已打开情况下会`ofReadOnly`标志。<br />- [Imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)方法用于打开该文件的元数据部分。<br />-该文件不是可移植可执行 (PE) 文件。 **注意：**这些条件依赖于 CLR 实现中，和可能削弱在将来 CLR 的版本。|  
  
## <a name="remarks"></a>备注  
 内存的`ppvData`指向是有效的只要基础元数据范围内处于打开状态。  
  
 按顺序才能起作用，当你将磁盘上文件的元数据映射到内存中通过调用此方法[imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法，你必须指定`ofReadOnly`标志，你必须指定`ofWrite`或`ofCopyMemory`标志。  
  
 特定于给定的 CLR 实现的每个作用域的文件映射类型选择。 它不能通过用户设置。 CLR 的当前实现始终返回`fmFlat`中`pdwMappingType`，但这可能会更改在将来版本的 CLR，或在将来的给定版本的服务版本。 你应始终检查返回的值， `pdwMappingType`，因为不同的类型将具有不同的布局和偏移量。  
  
 不支持传递对于所有三个参数为 NULL。 该方法返回`E_INVALIDARG`，并无输出来填充。 忽略映射类型或区域的大小可能会导致程序的异常终止。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataInfo 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [CorFileMapping 枚举](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
