---
title: "&lt;Type&gt;元素 (.NET Native)&lt;/Type&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
caps.latest.revision: 33
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 33
---
# &lt;Type&gt;元素 (.NET Native)&lt;/Type&gt;
将运行时策略应用到一个特定类型，例如一个类或结构。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Type Name="type_name"  
      Activate="policy_type"  
      Browse="policy_type"  
      Dynamic="policy_type"  
      Serialize="policy_type"   
      DataContractSerializer="policy_setting"  
      DataContractJsonSerializer="policy_setting"  
      XmlSerializer="policy_setting"  
      MarshalObject="policy_setting"  
      MarshalDelegate="policy_setting"  
      MarshalStructure="policy_setting" />  
  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|特性类型|说明|  
|---------------|--------------------|-----------------|  
|`Name`|常规|必需的特性。 指定类型名称。|  
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
|*类型 _ 名称*|类型名称。 如果此`<Type>`元素是任一子[ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md)元素或另一个`<Type>`元素， *type_name*可以包括而无需其命名空间的类型的名称。 否则为*类型 _ 名称*必须包含完全限定的类型名称。|  
  
## <a name="all-other-attributes"></a>所有其他特性  
  
|值|描述|  
|-----------|-----------------|  
|*policy_setting*|该设置将应用到这种策略类型。 可能值为 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 以及 `Required All`。 有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)|如果包含类型是一个特性，为该特性所应用到的代码元素定义一个运行时策略。|  
|[<>\>](../../../docs/framework/net-native/event-element-net-native.md)|将反射策略应用到属于这种类型的一个事件。|  
|[<>\>](../../../docs/framework/net-native/field-element-net-native.md)|将反射策略应用到属于这种类型的一个字段。|  
|[<>\>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|将策略应用到一个泛型类型的参数类型。|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|如果该策略已应用到以包含 `<Type>` 元素为代表的类型，将该策略应用到一个类型。|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|将反射策略应用到属于这种类型的一个方法。|  
|[<>\>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|将反射策略应用到属于这种类型的一个构造泛型方法。|  
|[<>\>](../../../docs/framework/net-native/property-element-net-native.md)|将反射策略应用到属于这种类型的一个属性。|  
|[<>\>](../../../docs/framework/net-native/subtypes-element-net-native.md)|将运行时策略应用到从包含类型继承的所有类。|  
|`<Type>`|将反射策略应用到一个嵌套类型。|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|将反射策略应用到一个构造泛型类型。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/application-element-net-native.md)|作为应用程序范围内的类型和元数据可以反应在运行时间的类型成员的容器而服务。|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|将反射策略应用到指定程序集中的所有类型。|  
|[<>\>](../../../docs/framework/net-native/library-element-net-native.md)|定义包含元数据在运行时间可以用于反射的类型和类型成员的程序集。|  
|[<>\>](../../../docs/framework/net-native/namespace-element-net-native.md)|将反射策略应用到命名空间中的所有类型。|  
|`<Type>`|将反射策略应用到一种类型及其所有成员。|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|将反射策略应用到一种构造泛型类型及其所有成员。|  
  
## <a name="remarks"></a>备注  
 反射、序列化和互操作特性都是可选项。 如果这些都不存在，`<Type>` 元素会充当容器，其子类型为独立成员定义策略。  
  
 如果`<Type>`元素是子[ <> \</> \> ](../../../docs/framework/net-native/assembly-element-net-native.md)， [ <> \</> \> ](../../../docs/framework/net-native/namespace-element-net-native.md)， `<Type>`，或[ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)元素，它会替代由父元素定义的策略设置。  
  
 一个泛型类型的 `<Type>` 元素会将其策略应用到所有不具有自身策略的实例化。 构造泛型类型的策略定义由[ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)元素。  
  
 如果该类型是泛型类型，其名称修饰重读音符 (' ') 跟着其泛型参数的编号。 例如，`Name`属性`<Type>`元素<xref:System.Collections.Generic.List%601?displayProperty=fullName>类显示为`Name="System.Collections.Generic.List`1"。  
  
## <a name="example"></a>示例  
 下面的示例使用反射显示字段、 属性和方法有关的信息<xref:System.Collections.Generic.List%601?displayProperty=fullName>类。 该变量`b`在示例中是[TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx)控件。 因为实例仅仅检索了类型信息，元数据的可用性是由 `Browse` 策略设置控制的。  
  
 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]  
  
 因为元数据<xref:System.Collections.Generic.List%601>类不会自动包括由[!INCLUDE[net_native](../../../includes/net-native-md.md)]工具链之中，该示例不能在运行时显示请求的成员信息。 为提供所需的元数据，将以下 `<Type>` 元素添加到运行时指令文件。 请注意，因为我们已经提供了父[ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md)元素中，我们不需要提供完全限定的类型名称在`<Type>`元素。  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="*Application*" Dynamic="Required All" />  
      <Namespace Name ="System.Collections.Generic" >  
        <Type Name="List`1" Browse="Required All" />   
     </Namespace>  
   </Application>  
</Directives>  
  
```  
  
## <a name="example"></a>示例  
 下面的示例使用反射来检索<xref:System.Reflection.PropertyInfo>对象，表示<xref:System.String.Chars%2A?displayProperty=fullName>属性。 然后，它使用[PropertyInfo.GetValue (对象、 对象\<xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=fullName>方法来检索在字符串中，第七个字符的值，并在字符串中显示的所有字符。 该变量`b`在示例中是[TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx)控件。  
  
 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]  
  
 因为元数据<xref:System.String>对象不可用，调用[PropertyInfo.GetValue (对象，对象\<xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=fullName>方法抛出异常<xref:System.NullReferenceException>异常在运行时使用编译时间[!INCLUDE[net_native](../../../includes/net-native-md.md)]工具链。 要消除异常并提供必需的元数据，请将以下 `<Type>` 元素添加到运行时指令文件：  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
    <Type Name="System.String" Dynamic="Required Public"/> -->  
  </Application>  
</Directives>  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [运行时指令 (rd.xml) 配置文件引用](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [运行时指令元素](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)