---
title: "IMetaDataDispenserEx::SetOption 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.SetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a58ac4379522c13125f98df058cd67bceb7cdbd1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption 方法
将指定的选项设置为当前的元数据范围的给定值。 选项控制如何处理对当前的元数据范围的调用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `optionId`  
 [in]指向用于指定要设置的选项的 GUID 的指针。  
  
 `pValue`  
 [in]要使用将选项设置的值。 此值的类型必须是类型的指定的选项的变体。  
  
## <a name="remarks"></a>备注  
 下表列出了可用的 Guid，`optionId`参数可以指向和有效的相应值`pValue`参数。  
  
|GUID|描述|`pValue`参数|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|控制哪些项检查重复项。 每次调用[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)创建新项的方法，你可以要求检查项目是否已存在当前作用域中的方法。 例如，你可以检查是否存在`mdMethodDef`项; 在这种情况下，当调用[imetadataemit:: Definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)，它将检查，该方法不存在当前作用域中。 此检查将使用唯一标识给定的方法的密钥： 父类型、 名称和签名。|必须是变体类型 UI4，并且必须包含的值的组合[CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md)枚举。|  
|MetaDataRefToDefCheck|控制哪些引用项转换为定义。 默认情况下，元数据引擎将通过将引用的项转换为其定义中，如果在当前范围中实际定义引用的项优化的代码。|必须是变体类型 UI4，并且必须包含的值的组合[CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md)枚举。|  
|MetaDataNotificationForTokenMovement|控制哪些令牌重新映射发生在元数据合并期间生成回调。 使用[imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)方法来建立你[IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)接口。|必须是变体类型 UI4，并且必须包含的值的组合[CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md)枚举。|  
|MetaDataSetENC|控件的编辑并继续 (ENC) 的行为。 只有一种模式的行为可以设置一次。|必须是变体类型 UI4，并且必须包含的值[CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md)枚举。 值不是一个位屏蔽。|  
|MetaDataErrorIfEmitOutOfOrder|控制哪些发出-的无序错误生成回调。 发出无序的元数据不是严重错误;但是，如果发出元数据引擎偏好顺序中的元数据，元数据将更为精简，因此可以更有效地搜索。 使用`IMetaDataEmit::SetHandler`方法来建立你[IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)接口。|必须是变体类型 UI4，并且必须包含的值的组合[CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md)枚举。|  
|MetaDataImportOption|控制在 ENC 过程中删除的项的种类检索枚举器。|必须是变体类型 UI4，并且必须包含的值的组合[CorImportOptions 枚举](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md)枚举。|  
|MetaDataThreadSafetyOptions|控制元数据引擎是否获取读取器/编写器锁，从而确保线程安全。 默认情况下，该引擎假定访问是单线程方式由调用方，因此会不获取任何锁。 客户端负责维护合适的线程同步时使用元数据 API。|必须是变体类型 UI4，并且必须包含的值[CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md)枚举。 值不是一个位屏蔽。|  
|MetaDataGenerateTCEAdapters|控件类型库导入程序是否应生成 COM 连接点容器的紧密耦合的事件 (TCE) 适配器。|必须是类型 BOOL 的变体。 如果`pValue`设置为`true`，类型库导入程序将生成 TCE 适配器。|  
|MetaDataTypeLibImportNamespace|指定要导入的类型库的非默认命名空间。|必须是一个 null 值或的变体类型 BSTR。 如果`pValue`为 null 值，当前命名空间设置为空; 否则为当前命名空间设置为保存在变量的 BSTR 类型中的字符串。|  
|MetaDataLinkerOptions|控制链接器是否应生成程序集或.NET Framework 模块文件。|必须是变体类型 UI4，并且必须包含的值的组合[CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md)枚举。|  
|MetaDataRuntimeVersion|指定公共语言运行时对其生成此映像的版本。 版本存储为一个字符串，例如"v1.0.3705"。|必须是一个 null 值、 VT_EMPTY 值或类型 BSTR 的变体。 如果`pValue`是运行时版本设置为 null，为 null。 如果`pValue`是 VT_EMPTY 的版本设置为默认值，该值从元数据的代码运行其中的 Mscorwks.dll 版本绘制。 否则，运行时版本设置为保存在变量的 BSTR 类型中的字符串。|  
|MetaDataMergerOptions|指定合并元数据的选项。|必须是变体类型 UI4，并且必须包含的值的组合`MergeFlags`CorHdr.h 文件中描述的枚举。|  
|MetaDataPreserveLocalRefs|禁用优化定义的本地引用。|必须包含的值的组合[CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md)枚举。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
