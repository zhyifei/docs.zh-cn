---
title: "&lt;Method&gt;元素 (.NET Native)&lt;/Method&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# &lt;Method&gt;元素 (.NET Native)&lt;/Method&gt;
将运行时反射策略应用到一个构造函数或方法。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|特性类型|描述|  
|---------------|--------------------|-----------------|  
|`Name`|常规|必需的特性。 指定方法名称。|  
|`Signature`|常规|可选特性。 指定方法签名。 如果存在多个参数，它们之间用逗号分割。 例如，以下`<Method>`元素定义策略<xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29>方法。<br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> 如果该特性不存在，运行时指令将应用到该方法的所有重载。|  
|`Browse`|映像|可选特性。 控制对该方法信息的查询或列举该方法，但并不在运行时间启用任何动态调用。|  
|`Dynamic`|映像|可选特性。 控制运行时对构造函数或方法的访问，以启用动态编程。 该策略确保一个成员可在运行时间内得到调用。|  
  
## <a name="name-attribute"></a>Name 特性  
  
|值|说明|  
|-----------|-----------------|  
|*method_name*|方法名。 该方法的类型定义由容器的父[ <> \> ](../../../docs/framework/net-native/type-element-net-native.md)或[ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)元素。|  
  
## <a name="signature-attribute"></a>签名特性  
  
|值|描述|  
|-----------|-----------------|  
|*method_signature*|形成方法签名的参数类型。 多个参数由逗号分隔，例如，`"System.String,System.Int32,System.Int32)"`。 参数类型名称应是完全限定的。|  
  
## <a name="all-other-attributes"></a>所有其他特性  
  
|值|说明|  
|-----------|-----------------|  
|*policy_setting*|该设置将应用到这种策略类型。 可能值为 `Auto`、`Excluded`、`Included` 和 `Required`。 有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/parameter-element-net-native.md)|将策略应用到传递到方法的自变量类型。|  
|[<>\>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|将策略应用到一个泛型类型或方法的参数类型。|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|如果该策略已应用到以包含 `<Method>` 元素为代表的方法，将该策略应用到一个类型。|  
|[<>\>](../../../docs/framework/net-native/typeparameter-element-net-native.md)|将策略应用到所表示的类型<xref:System.Type>参数传递给方法。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|将反射策略应用到一种类型及其所有成员。|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|将反射策略应用到一种构造泛型类型及其所有成员。|  
  
## <a name="remarks"></a>备注  
 一个泛型方法的 `<Method>` 元素会将其策略应用到所有不具有自身策略的实例化。  
  
 你可以使用 `Signature` 特性为特定的方法重载指定策略。 如果 `Signature` 特性不存在，运行时指令将应用到该方法的所有重载。  
  
 你无法通过使用 `<Method>` 元素为一个构造函数定义运行时反射策略。 Instead, use the `Activate` attribute of the  [<>\>](../../../docs/framework/net-native/assembly-element-net-native.md), [<>\>](../../../docs/framework/net-native/namespace-element-net-native.md), [<>\>](../../../docs/framework/net-native/type-element-net-native.md), or [<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.  
  
## <a name="example"></a>示例  
 以下实例中的 `Stringify` 方法是使用反射将一个对象转化为其字符串表示形式的一个通用格式化方法。 除了调用该对象的默认`ToString`方法，则此方法可以生成格式化的结果字符串，通过将对象传递`ToString`方法格式字符， <xref:System.IFormatProvider>实现，或者两者。 它也可以调用其中一个<xref:System.Convert.ToString%2A?displayProperty=fullName>将数字转换为其二进制、 十六进制或八进制表示形式的重载。  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 `Stringify` 方法可以通过类似以下的代码调用：  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 但是，当使用.NET 本机编译，该示例可以引发的异常数在运行时，包括<xref:System.NullReferenceException>和[MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)例外情况之外，这是因为`Stringify`方法主要用于支持.NET Framework 类库中的基元类型的动态格式化。 然而，它们的元数据不会通过默认指令文件变得可以使用。 然而，即使它们的元数据在可用时，该示例引发[MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)异常因为相应`ToString`实现并不包含在本机代码中。  
  
 这些异常可以全部除去使用[ <> \> ](../../../docs/framework/net-native/type-element-net-native.md)元素来定义那些元数据必须存在，并通过添加的类型`<Method>`元素以确保方法的实现重载可动态调用也是存在。 以下的 default.rd.xml 文件可以清除这些异常并允许实例没有错误地执行。  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [运行时指令 (rd.xml) 配置文件引用](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [运行时指令元素](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [<>\>元素](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)