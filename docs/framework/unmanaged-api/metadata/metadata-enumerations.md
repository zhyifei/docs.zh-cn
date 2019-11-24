---
title: 元数据枚举
ms.date: 03/30/2017
helpviewer_keywords:
- enumerations [.NET Framework metadata]
- metadata enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], metadata
ms.assetid: 711ab251-cfdb-4280-aaa6-9bc1b341cdc3
ms.openlocfilehash: 92f2419070738a49f78c1f1497652cc0b89f3b21
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447859"
---
# <a name="metadata-enumerations"></a>元数据枚举
本节描述元数据 API 使用的非托管枚举。  
  
## <a name="in-this-section"></a>本节内容  
 [AssemblyFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)  
 包含一些值，用于描述程序集的运行时函数。  
  
 [AssemblyRefFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)  
 包含一些值，用于描述程序集引用的函数。  
  
 [CeeSectionAttr 枚举](../../../../docs/framework/unmanaged-api/metadata/ceesectionattr-enumeration.md)  
 Provides values that specify the attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.  
  
 [CeeSectionRelocType 枚举](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md)  
 Provides values to influence the type of `reloc` instruction emitted in a call to the [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md) method.  
  
 [COINITICOR 枚举](../../../../docs/framework/unmanaged-api/metadata/coiniticor-enumeration.md)  
 Specifies constants used by [CoInitializeCor](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md) when initializing the common language runtime.  
  
 [COINITIEE 枚举](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md)  
 Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.  
  
 [CorArgType 枚举](../../../../docs/framework/unmanaged-api/metadata/corargtype-enumeration.md)  
 包含一些值，用于描述运行时句柄的本机类型。  
  
 [CorAssemblyFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)  
 包含一些值，用于描述应用于程序集编译的元数据。  
  
 [CorAttributeTargets 枚举](../../../../docs/framework/unmanaged-api/metadata/corattributetargets-enumeration.md)  
 指定可应用属性的应用程序元素。  
  
 [CorCallingConvention 枚举](../../../../docs/framework/unmanaged-api/metadata/corcallingconvention-enumeration.md)  
 包含一些值，用于描述托管代码中执行的调用约定类型。  
  
 [CorCheckDuplicatesFor 枚举](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md)  
 包含检查重复期间使用的值。  
  
 [CorDeclSecurity 枚举](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)  
 包含一些值，用于描述公共语言运行时使用的声明性安全类型。  
  
 CorElementType  
 包含一些值，用于描述公共语言运行时的基础本机类型 <xref:System.Type>。  
  
 [CorErrorIfEmitOutOfOrder 枚举](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md)  
 包含一些标志值，用于指示无序发出元数据时应生成错误消息的条件。  
  
 [CorEventAttr 枚举](../../../../docs/framework/unmanaged-api/metadata/coreventattr-enumeration.md)  
 包含一些值，用于描述事件的元数据。  
  
 [CorFieldAttr 枚举](../../../../docs/framework/unmanaged-api/metadata/corfieldattr-enumeration.md)  
 包含一些值，用于描述字段的相应元数据。  
  
 [CorFileFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)  
 Contains values that describe the type of file defined in a call to the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.  
  
 [CorFileMapping 枚举](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)  
 Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.  
  
 [CorGenericParamAttr 枚举](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)  
 Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to the [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md) method.  
  
 [CorImportOptions 枚举](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md)  
 包含一些标志值，用于在导入当前作用域范围外的程序集的过程中控制行为。  
  
 [CorLinkerOptions 枚举](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md)  
 指定用于选择元数据链接器的选项的标志。  
  
 [CorLocalRefPreservation 枚举](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md)  
 包含用于处理本地引用的标志值。  
  
 [CorManifestResourceFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md)  
 包含一些值，用于描述程序集清单中编码的资源的可见性。  
  
 [CorMethodAttr 枚举](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)  
 包含一些值，用于描述方法的相应元数据。  
  
 [CorMethodImpl 枚举](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)  
 包含一些值，用于描述方法实现功能。  
  
 [CorMethodSemanticsAttr 枚举](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md)  
 包含一些值，用于描述方法和关联属性或事件之间的关系。  
  
 [CorNativeLinkFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)  
 提供链接本机代码时链接器使用的标志值。  
  
 [CorNativeLinkType 枚举](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 提供一些值，用于指示本机代码中链接的类型。  
  
 [CorNativeType 枚举](../../../../docs/framework/unmanaged-api/metadata/cornativetype-enumeration.md)  
 包含一些值，用于描述本机非托管类型。  
  
 [CorNotificationForTokenMovement 枚举](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md)  
 包含会影响标记移动的相应通知的标志值。  
  
 [CorOpenFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)  
 包含一些标志值，用于控制打开清单文件时的元数据行为。  
  
 [CorParamAttr 枚举](../../../../docs/framework/unmanaged-api/metadata/corparamattr-enumeration.md)  
 包含一些值，用于描述方法参数的元数据。  
  
 [CorPEKind 枚举](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)  
 Contains values that describe a portable executable file, as returned from a call to the [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md) method.  
  
 [CorPinvokeMap 枚举](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md)  
 包含一些值，用于描述 PInvoke 调用的功能。  
  
 [CorPropertyAttr 枚举](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)  
 包含一些值，用于描述属性的元数据。  
  
 [CorRefToDefCheck 枚举](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md)  
 指定用于控制将哪些引用项转换为相应定义以优化代码的标志。  
  
 [CorRegFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/corregflags-enumeration.md)  
 提供安装模块或复合项时注册所使用的标志值。  
  
 [CorSaveSize 枚举](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md)  
 包含一些值，用于指示查询保存操作的大小时所需的精度级别。  
  
 [CorSerializationType 枚举](../../../../docs/framework/unmanaged-api/metadata/corserializationtype-enumeration.md)  
 包含一些值，用于描述公共语言运行时如何序列化对象。 These values generally correspond to CorElementType values.  
  
 [CorSetENC 枚举](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md)  
 包含一些值，用于在元数据生成期间影响行为。  
  
 [CorThreadSafetyOptions 枚举](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md)  
 指定用于选择线程安全性选项的标志。  
  
 [CorTokenType 枚举](../../../../docs/framework/unmanaged-api/metadata/cortokentype-enumeration.md)  
 包含一些值，用于指示元数据标记引用的对象类型。  
  
 [CorTypeAttr 枚举](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)  
 包含一些值，用于指示类型元数据。  
  
 [CorUnmanagedCallingConvention 枚举](../../../../docs/framework/unmanaged-api/metadata/corunmanagedcallingconvention-enumeration.md)  
 包含一些值，用于描述非托管的调用约定。  
  
 [CorValidatorModuleType 枚举](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md)  
 Provides values used by the [IMetaDataValidate](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md) interface to specify the type of the module (PE file vs. .obj file).  
  
 [COUNINITIEE 枚举](../../../../docs/framework/unmanaged-api/metadata/couninitiee-enumeration.md)  
 Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.  
  
## <a name="related-sections"></a>相关章节  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
  
 [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)  
  
 [元数据结构](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
  
 [元数据联合](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
