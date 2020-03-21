---
title: IMetaDataInfo::GetFileMapping 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175260"
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping 方法
获取映射文件的内存区域和映射类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>parameters  
 `ppvData`  
 [出]指向映射文件开头的指针。  
  
 `pcbData`  
 [出]映射区域的大小。 如果是`pdwMappingType``fmFlat`，则这是文件的大小。  
  
 `pdwMappingType`  
 [出]指示映射类型的[CorFile 映射](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)值。 公共语言运行时 （CLR） 的当前实现始终返回`fmFlat`。 保留其他值以供将来使用。 但是，应始终验证返回的值，因为将来的版本或服务版本中可能会启用其他值。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|`S_OK`|所有输出都已填充。|  
|`E_INVALIDARG`|NULL 作为参数值传递。|  
|`COR_E_NOTSUPPORTED`|CLR 实现不能提供有关内存区域的信息。 这可能是由以下原因引起的：<br /><br /> - 元数据作用域已打开`ofWrite`，`ofCopyMemory`或 标志。<br />- 元数据作用域在没有`ofReadOnly`标志的情况下打开。<br />- [IMetaDataDispenser：：OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)方法仅用于打开文件的元数据部分。<br />- 该文件不是可移植可执行文件 （PE）。 **注：** 这些条件取决于 CLR 实现，并且将来版本的 CLR 可能会减弱。|  
  
## <a name="remarks"></a>备注  
 只要基础元数据`ppvData`作用域处于打开状态，指向的内存才有效。  
  
 为了使此方法正常工作，当您通过调用[IMetaDataDispenser：：openScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法将磁盘文件的元数据映射到内存时，必须指定`ofReadOnly`标志，并且不能指定`ofWrite`或`ofCopyMemory`标志。  
  
 每个作用域的文件映射类型的选择特定于 CLR 的给定实现。 用户无法设置它。 CLR 的当前实现始终在`fmFlat`中`pdwMappingType`返回，但这可能在 CLR 的未来版本或给定版本的将来服务版本中更改。 应始终在 中`pdwMappingType`检查返回的值，因为不同类型的布局和偏移量将不同。  
  
 不支持为三个参数中的任何一个传递 NULL。 该方法返回`E_INVALIDARG`，并且不会填充任何输出。 忽略映射类型或区域大小可能会导致异常程序终止。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataInfo 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [CorFileMapping 枚举](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
