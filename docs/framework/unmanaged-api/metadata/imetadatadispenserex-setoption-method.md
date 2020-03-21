---
title: IMetaDataDispenserEx::SetOption 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
ms.openlocfilehash: f8e85a670d04e5825653864484b7ccd9ce747949
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175897"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption 方法
将指定选项设置为当前元数据作用域的给定值。 该选项控制如何处理对当前元数据作用域的调用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>parameters  
 `optionId`  
 [在]指向 GUID 的指针，用于指定要设置的选项。  
  
 `pValue`  
 [在]用于设置选项的值。 此值的类型必须是指定选项类型的变体。  
  
## <a name="remarks"></a>备注  
 下表列出了`optionId`参数可以指向的可用 GUID 以及`pValue`参数的相应有效值。  
  
|GUID|说明|`pValue`参数|  
|----------|-----------------|------------------------|  
|元数据检查重复项|控制检查哪些项的重复项。 每次调用创建新项目的[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)方法时，都可以要求该方法检查该项是否已存在于当前作用域中。 例如，您可以检查`mdMethodDef`是否存在项目;例如，可以检查是否存在项目。在这种情况下，当您调用[IMetaDataEmit：:DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)时，它将检查该方法是否不存在在当前作用域中。 此检查使用唯一标识给定方法的键：父类型、名称和签名。|必须是类型 UI4 的变体，并且必须包含[CorCheck 复制项的值的组合。For](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md)枚举。|  
|元数据参考检查|引用项的控件将转换为定义。 默认情况下，如果引用的项实际上是在当前作用域中定义的，元数据引擎将通过将引用的项转换为其定义来优化代码。|必须是类型 UI4 的变体，并且必须包含[CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md)枚举的值的组合。|  
|元数据通知令牌移动|控制在元数据合并期间发生的令牌重映射生成回调。 使用[IMetaDataEmit：：SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)方法建立[IMapToken 接口](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)。|必须是类型 UI4 的变体，并且必须包含[Cor通知ForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md)枚举的值的组合。|  
|元数据集|控制编辑和继续 （ENC） 的行为。 一次只能设置一种行为模式。|必须是类型 UI4 的变体，并且必须包含[CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md)枚举的值。 该值不是位掩码。|  
|元数据错误，如果已发出命令|控制发出订单外错误生成回调。 按顺序发出元数据并非致命;但是，如果按元数据引擎青睐的顺序发出元数据，则元数据将更加紧凑，因此可以更有效地搜索元数据。 使用`IMetaDataEmit::SetHandler`方法建立[IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)界面。|必须是类型 UI4 的变体，并且必须包含[CorErrorIfEmitOutOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md)枚举的值的组合。|  
|元数据导入选项|控制枚举器检索在 ENC 期间删除的哪些类型的项。|必须是类型 UI4 的变体，并且必须包含[CorImportOptions 枚举](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md)枚举的值的组合。|  
|元数据线程安全选项|控制元数据引擎是否获取读取器/写入器锁，从而确保线程安全。 默认情况下，引擎假定访问由调用方单线程进行，因此不会获取锁。 客户端负责在使用元数据 API 时保持正确的线程同步。|必须是类型 UI4 的变体，并且必须包含[CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md)枚举的值。 该值不是位掩码。|  
|元数据生成适配器|控制类型库导入器是否应为 COM 连接点容器生成紧密耦合的事件 （TCE） 适配器。|必须是 BOOL 类型的变体。 如果`pValue`设置为`true`，类型库导入器将生成 TCE 适配器。|  
|MetaDataTypeLib导入命名空间|为要导入的类型库指定非默认命名空间。|必须为空值或 BSTR 类型的变体。 如果`pValue`为空值，则当前命名空间设置为 null;如果为 null。"如果为空"，则为 null。否则，当前命名空间将设置为在变体的 BSTR 类型中持有的字符串。|  
|元数据链接器选项|控制链接器是生成程序集还是 .NET 框架模块文件。|必须是类型 UI4 的变体，并且必须包含[CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md)枚举的值的组合。|  
|元数据运行时版本|指定生成此映像的通用语言运行时的版本。 版本存储为字符串，如"v1.0.3705"。|必须为空值、VT_EMPTY值或 BSTR 类型的变体。 如果`pValue`为 null，则运行时版本设置为 null。 如果`pValue`VT_EMPTY，则版本设置为默认值，该值从运行元数据代码的 Mscorwks.dll 版本中提取。 否则，运行时版本将设置为在变体的 BSTR 类型中持有的字符串。|  
|元数据合并选项|指定合并元数据的选项。|必须是类型 UI4 的变体，并且必须包含枚举值`MergeFlags`的组合，这在 CorHdr.h 文件中描述。|  
|MetaData 保留本地引用|禁用将本地引用优化到定义中。|必须包含[CorLocalRef 保存](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md)枚举的值的组合。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
