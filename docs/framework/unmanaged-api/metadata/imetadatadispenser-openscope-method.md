---
title: IMetaDataDispenser::OpenScope 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175936"
---
# <a name="imetadatadispenseropenscope-method"></a>IMetaDataDispenser::OpenScope 方法
打开现有的磁盘文件并将其元数据映射到内存中。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>parameters  
 `szScope`  
 [在]要打开的文件的名称。 该文件必须包含通用语言运行时 （CLR） 元数据。  
  
 `dwOpenFlags`  
 [在][CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)枚举的值，用于指定打开的模式（读取、写入等）。  
  
 `riid`  
 [在]要返回的所需元数据接口的 IID;调用方将使用接口导入（读取）或发出（写入）元数据。  
  
 的值`riid`必须指定其中一个"导入"或"发射"接口。 有效值IID_IMetaDataEmit、IID_IMetaDataImport、IID_IMetaDataAssemblyEmit、IID_IMetaDataAssemblyImport、IID_IMetaDataEmit2或IID_IMetaDataImport2。  
  
 `ppIUnk`  
 [出]指向返回接口的指针。  
  
## <a name="remarks"></a>备注  
 可以使用"导入"接口之一的方法查询元数据的内存副本，也可以添加到使用"emit"接口之一的方法。  
  
 如果目标文件不包含 CLR 元数据，则`OpenScope`该方法将失败。  
  
 在 .NET 框架版本 1.0 和版本 1.1 中，`dwOpenFlags`如果使用设置为 Read 打开作用域，则它有资格共享。 也就是说，如果后续调用以`OpenScope`以前打开的文件的名称传递，则重用现有作用域，并且不会创建新的数据结构集。 但是，由于这种共享，可能会出现问题。  
  
 在 .NET 框架版本 2.0 中，`dwOpenFlags`不再共享使用设置为 Read 打开的作用域。 使用 ReadOnly 值允许共享作用域。 共享作用域时，使用"读/写"元数据接口的查询将失败。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
