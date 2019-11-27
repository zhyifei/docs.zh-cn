---
title: IMetaDataDispenser::OpenScopeOnMemory 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 04e0fabfc0d70c9d922e0715f32bd07237ce8741
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442311"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>IMetaDataDispenser::OpenScopeOnMemory 方法
打开包含现有元数据的内存区域。 也就是说，此方法将打开一个指定的内存区域，其中的现有数据将被视为元数据。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>参数  
 `pData`  
 中指定内存区域起始地址的指针。  
  
 `cbData`  
 中内存区域的大小（以字节为单位）。  
  
 `dwOpenFlags`  
 中[CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)枚举的值，该值指定用于打开的模式（读取、写入等）。  
  
 `riid`  
 中要返回的所需元数据接口的 IID;调用方将使用接口导入（读取）或发出（写入）元数据。  
  
 `riid` 的值必须指定一个 "导入" 或 "发出" 接口。 有效值为 IID_IMetaDataEmit、IID_IMetaDataImport、IID_IMetaDataAssemblyEmit、IID_IMetaDataAssemblyImport、IID_IMetaDataEmit2 或 IID_IMetaDataImport2。  
  
 `ppIUnk`  
 弄指向返回的接口的指针。  
  
## <a name="remarks"></a>备注  
 可以使用 "导入" 接口中的方法查询元数据的内存中副本，或使用 "发出" 接口之一中的方法将其添加到中。  
  
 `OpenScopeOnMemory` 方法类似于[IMetaDataDispenser：： OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法，不同之处在于相关元数据已存在于内存中，而不是磁盘上的文件中。  
  
 如果内存的目标区域不包含公共语言运行时（CLR）元数据，则 `OpenScopeOnMemory` 方法将失败。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
