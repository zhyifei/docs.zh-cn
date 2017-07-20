---
title: "应用互操作特性 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - ".NET Framework, 向 COM 公开组件"
  - "特性 [.NET Framework], 转换工具"
  - "特性 [.NET Framework], 设计时功能"
  - "特性 [.NET Framework], 互操作特定"
  - "COM 互操作, 应用特性"
  - "COM 互操作, 公开 COM 组件"
  - "转换工具特性"
  - "设计时特性"
  - "与非托管代码间的互操作, 应用特性"
  - "与非托管代码间的互操作, 公开 .NET Framework 组件"
ms.assetid: b6014613-641c-4912-9e2f-83a99210a037
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 应用互操作特性
<xref:System.Runtime.InteropServices> 命名空间提供了三种类别的互操作特定特性：您在设计时应用的特性、COM 互操作工具和 API 在转换过程中应用的特性，以及您或 COM 互操作应用的特性。  
  
 如果您不熟悉将特性应用于托管代码这一任务，请参见[利用特性扩展元数据](../../../docs/standard/attributes/index.md)。  与其他自定义特性类似，Interop 特定的特性可以应用于类型、方法、属性、参数、字段和其他成员。  
  
## 设计时特性  
 利用设计时特性，可以调整 COM 互操作工具和 API 所执行的转换过程的结果。  下表将说明可应用于托管源代码的特性。  有时，COM 互操作工具也可能会应用下表所述的特性。  
  
|特性|说明|  
|--------|--------|  
|<xref:System.Runtime.InteropServices.AutomationProxyAttribute>|指定是否应该使用自动化封送拆收器或自定义代理及存根 \(Stub\) 对该类型进行封送处理。|  
|<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>|控制为类生成的接口类型。|  
|<xref:System.Runtime.InteropServices.CoClassAttribute>|标识从类型库导入的初始 coclass 的 CLSID。<br /><br /> COM 互操作工具通常应用此特性。|  
|<xref:System.Runtime.InteropServices.ComImportAttribute>|指示 coclass 或接口定义是从 COM 类型库导入的。  运行时利用此标志来确定如何激活和封送类型。  该特性禁止将类型导回类型库。<br /><br /> COM 互操作工具通常应用此特性。|  
|<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>|指示应该在注册程序集（使其可从 COM 中使用）时调用方法，以便在注册过程中执行用户编写的代码。|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|标识作为类事件源代码的接口。<br /><br /> COM 互操作工具可应用此特性。|  
|<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>|指定应该在从 COM 中注销程序集时调用方法，以便在此过程中执行用户编写的代码。|  
|<xref:System.Runtime.InteropServices.ComVisibleAttribute>|使类型在特性值等于 **false** 时对于 COM 不可见。  可以向单个类型或整个程序集应用此特性，以控制 COM 可见性。  默认情况下，所有托管的公共类型都是可见的，因此不需要使用该特性来使其变为可见。|  
|<xref:System.Runtime.InteropServices.DispIdAttribute>|指定方法或字段的 COM 调度标识符 \(DISPID\)。  该特性包含它所描述的方法、字段或属性的 DISPID。<br /><br /> COM 互操作工具可应用此特性。|  
|<xref:System.Runtime.InteropServices.FieldOffsetAttribute>|指示当与 **StructLayoutAttribute** 一起使用且将 **LayoutKind** 设置为 Explicit 时，每个字段在类中的物理位置。|  
|<xref:System.Runtime.InteropServices.GuidAttribute>|指定类、接口或整个类型库的全局唯一标识符 \(GUID\)。  传递给特性的字符串必须为类型 **System.Guid** 可接受的构造函数参数格式。<br /><br /> COM 互操作工具可应用此特性。|  
|[IDispatchImpAttribute](frlrfsystemruntimeinteropservicesidispatchimplattributeclasstopic)|指示当向 COM 公开双重接口和调度接口时公共语言运行时使用何种 **IDispatch** 接口实现。|  
|<xref:System.Runtime.InteropServices.InAttribute>|指示应将数据封送到调用方中。  可用于表示参数的特性。|  
|<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>|控制如何向 COM 客户端（双重、由 IUnknown 导出或仅 IDispatch）公开托管接口。<br /><br /> COM 互操作工具可应用此特性。|  
|<xref:System.Runtime.InteropServices.LCIDConversionAttribute>|指示非托管方法签名需要 LCID 参数。<br /><br /> COM 互操作工具可应用此特性。|  
|<xref:System.Runtime.InteropServices.MarshalAsAttribute>|指示字段或参数中的数据应如何在托管和非托管代码之间封送。  由于每种数据类型都具有默认的封送行为，所以此特性始终是可选的。<br /><br /> COM 互操作工具可应用此特性。|  
|<xref:System.Runtime.InteropServices.OptionalAttribute>|指示参数是可选的。<br /><br /> COM 互操作工具可应用此特性。|  
|<xref:System.Runtime.InteropServices.OutAttribute>|指示字段或参数中的数据必须从被调用的对象封送回它的调用方。|  
|<xref:System.Runtime.InteropServices.PreserveSigAttribute>|防止通常在互用调用时发生的 HRESULT 或 retval 签名转换。  此特性将影响封送以及类型库导出。<br /><br /> COM 互操作工具可应用此特性。|  
|<xref:System.Runtime.InteropServices.ProgIdAttribute>|指定 .NET Framework 类的 ProgID。  可用于表示类的特性。|  
|<xref:System.Runtime.InteropServices.StructLayoutAttribute>|控制类的各字段的物理布局。<br /><br /> COM 互操作工具可应用此特性。|  
  
## 转换工具特性  
 下表将说明 COM 互操作工具在转换过程应用的特性。  这些特性不在设计时应用。  
  
|特性|说明|  
|--------|--------|  
|<xref:System.Runtime.InteropServices.ComAliasNameAttribute>|指示参数或字段类型的 COM 别名。  可用于表示参数、字段或返回值的特性。|  
|<xref:System.Runtime.InteropServices.ComConversionLossAttribute>|指示从类型库向程序集导入类或接口时丢失了有关信息。|  
|<xref:System.Runtime.InteropServices.ComEventInterfaceAttribute>|标识源接口和实现事件接口方法的类。|  
|<xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>|指示程序集最初是从 COM 类型库导入的。  此特性包含原类型库的类型库定义。|  
|<xref:System.Runtime.InteropServices.TypeLibFuncAttribute>|包含最初为此函数从 COM 类型库导入的 **FUNCFLAGS**。|  
|<xref:System.Runtime.InteropServices.TypeLibTypeAttribute>|包含最初为此类型从 COM 类型库导入的 **TYPEFLAGS**。|  
|<xref:System.Runtime.InteropServices.TypeLibVarAttribute>|包含最初为此变量从 COM 类型库导入的 **VARFLAGS**。|  
  
## 请参阅  
 <xref:System.Runtime.InteropServices>   
 [向 COM 公开 .NET Framework 组件](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [特性](../../../docs/standard/attributes/index.md)   
 [为互操作限定 .NET 类型](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [将 COM 的程序集打包](../../../docs/framework/interop/packaging-an-assembly-for-com.md)