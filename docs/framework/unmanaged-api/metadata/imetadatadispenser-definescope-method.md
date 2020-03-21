---
title: IMetaDataDispenser::DefineScope 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 2f9325f3795262a0c33af02f87fc5d3a020658cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177645"
---
# <a name="imetadatadispenserdefinescope-method"></a>IMetaDataDispenser::DefineScope 方法
在内存中创建一个新区域，您可以在其中创建新元数据。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>parameters  
 `rclsid`  
 [在]要创建的元数据结构版本的 CLSID。 此值必须CLSID_CorMetaDataRuntime .NET 框架版本 2.0。  
  
 `dwCreateFlags`  
 [在]指定选项的标志。 此值对于 .NET 框架 2.0 必须为零。  
  
 `riid`  
 [在]要返回的所需元数据接口的 IID;调用方将使用接口创建新元数据。  
  
 的值`riid`必须指定其中一个"emit"接口。 有效值IID_IMetaDataEmit、IID_IMetaDataAssemblyEmit 或IID_IMetaDataEmit2。  
  
 `ppIUnk`  
 [出]指向返回接口的指针。  
  
## <a name="remarks"></a>备注  
 `DefineScope`创建一组内存中元数据表，为元数据生成唯一 GUID（模块版本标识符或 MVID），并在模块表中为发出的编译单元创建一个条目。  
  
 您可以根据需要使用[IMetaDataEmit：setModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)或[IMetaDataEmit：:DefineCustom属性](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)方法将属性附加到整个元数据范围。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
