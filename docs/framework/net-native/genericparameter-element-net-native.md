---
title: "&lt;泛型参数&gt;元素 (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# &lt;泛型参数&gt;元素 (.NET Native)
将策略应用到一个泛型类型或方法的参数类型。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|特性类型|说明|  
|---------------|--------------------|-----------------|  
|`Name`|常规|必需的特性。 泛型参数的名称。 例如，对于泛型委托<xref:System.Func%603>，值`Name`属性为"TResult"将运行时策略应用于委托的返回值。\</T1, T2, TResult>|  
|`Activate`|映像|可选特性。 控制运行时对构造函数的访问，以启用实例激活。|  
|`Browse`|映像|可选特性。 控制对有关程序元素信息的查询，但并不启用任何运行时访问。|  
|`Dynamic`|映像|可选特性。 控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。|  
|`Serialize`|序列化|可选特性。 控制运行时对构造函数、字段和属性的访问，使类型实例得到序列化和反序列化处理，这是通过库进行的，例如 Newtonsoft JSON 序列化程序。|  
|`DataContractSerializer`|序列化|可选特性。 控制使用的序列化策略<xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName>类。|  
|`DataContractJsonSerializer`|序列化|可选特性。 控制使用的 JSON 序列化策略<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName>类。|  
|`XmlSerializer`|序列化|可选特性。 控制使用的 XML 序列化策略<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>类。|  
|`MarshalObject`|Interop|可选特性。 控制封送引用类型到 Windows 运行时和 COM 的策略。|  
|`MarshalDelegate`|Interop|可选特性。 控制将委托类型作为函数指针封送到本机代码的策略。|  
|`MarshalStructure`|Interop|可选特性。 控制封送处理值类型到本机代码的策略。|  
  
## <a name="name-attribute"></a>Name 特性  
  
|值|说明|  
|-----------|-----------------|  
|*generic_parameter_name*|必需的特性。 泛型类型参数的名称。 例如，对于泛型委托<xref:System.Func%603>、 *generic_parameter_name* "TResult"的值将运行时策略应用到该委托的返回值。\</T1, T2, TResult>|  
  
## <a name="all-other-attributes"></a>所有其他特性  
  
|值|描述|  
|-----------|-----------------|  
|*policy_setting*|该设置将应用到这种策略类型。 可能值为 `All`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。 有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|将运行时反射策略应用到一个构造函数或方法。|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|将运行时反射策略应用到一个特定类型，例如一个类或结构。|  
  
## <a name="remarks"></a>备注  
 `<GenericParameter>`元素是任一子[ <> \> ](../../../docs/framework/net-native/method-element-net-native.md)或[ <> \> ](../../../docs/framework/net-native/type-element-net-native.md)元素，用于将策略应用到特定的泛型类型参数，由泛型类型或方法签名中其名称指定。  
  
 `<GenericParameter>` 元素在同序列化程序一起使用时非常有用。 下面的示例使用`<GenericParameter>`元素将策略应用于类型`T`NewtonSoft JSON 序列化程序的调用中[JsonConvert.DeserializeObject<>\>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm)方法重载。  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [<>\>元素](../../../docs/framework/net-native/method-element-net-native.md)   
 [<>\>元素](../../../docs/framework/net-native/type-element-net-native.md)   
 [运行时指令 (rd.xml) 配置文件引用](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [运行时指令元素](../../../docs/framework/net-native/runtime-directive-elements.md)