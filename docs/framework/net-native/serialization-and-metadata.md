---
title: 序列化和元数据
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
ms.openlocfilehash: 7c6fe241fbf92f52abfa0eb66c37bff4d227b4e5
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81241914"
---
# <a name="serialization-and-metadata"></a>序列化和元数据

如果你的应用会序列化和反序列化对象，你可能需要将条目添加到运行时指令 (.rd.xml) 文件以确保必要的元数据在运行时间存在。 有两类序列化序列化程序，并且每一类要求在你的运行时指令文件中进行不同处理：  
  
- 基于反射的第三方序列化程序。 这些程序要求修改你的运行时指令文件，我们会在后面一部分对其进行讨论。  
  
- 在 .NET Framework 类库中找到的非基于反射的序列化程序。 这些程序可能要求修改运行时指令文件，我们会在 [Microsoft 序列化程序](#Microsoft)部分对其进行讨论。  
  
<a name="ThirdParty"></a>
## <a name="third-party-serializers"></a>第三方序列化程序

 Newtonsoft.JSON 等第三方序列化程序通常是基于反射的。 考虑到一个序列化数据的二进制大型对象 (BLOB)，该数据中的字段通过按名称查找目标类型的字段被分配到了一个具体类型。 在最低限度下，使用这些库时，在 `List<Type>` 集合中尝试序列化或反序列化的每个 <xref:System.Type> 对象都会出现 [MissingMetadataException](missingmetadataexception-class-net-native.md) 异常。  
  
 处理由这些序列化程序的丢失元数据引起的最简单的方法是，收集将被用在单独命名空间（比如 `App.Models`）下序列化中的类型，并向其直接应用一个 `Serialize` 元数据指令：  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 有关示例中使用的语法的信息，请参阅[\<命名空间>元素](namespace-element-net-native.md)。  
  
<a name="Microsoft"></a>
## <a name="microsoft-serializers"></a>Microsoft 序列化程序

 尽管 <xref:System.Runtime.Serialization.DataContractSerializer>、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 和 <xref:System.Xml.Serialization.XmlSerializer> 类并不依赖反射，它们需要在要得到序列化或反序列化的对象的基础上生成的代码。 每个序列化程序的重载构造函数包含一个指定需要得到序列化或反序列化的 <xref:System.Type> 参数。 你在代码中如何指定该类型定义了你必须进行的操作，这将在以下两部分中讨论到。  
  
### <a name="typeof-used-in-the-constructor"></a>构造函数中使用的 TypeOf

 如果调用这些序列化类的构造函数，并在方法调用中包括 C#[类型](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator)运算符，**则不必执行任何其他工作**。 例如，在以下对序列化类构造函数的每个调用中，`typeof` 关键字被用作了传递给构造函数的表达式的一部分。  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 .NET 本机编译器将自动处理此代码。  
  
### <a name="typeof-used-outside-the-constructor"></a>构造函数外部使用的 TypeOf

 如果调用这些序列化类的构造函数，并在提供给构造函数参数的<xref:System.Type>表达式之外使用 C# [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator)运算符，如以下代码中，.NET 本机编译器无法解决类型：  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 在这种情况下，你必须通过添加如下所示的条目指定在运行时指令文件中的类型：  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 同样，如果调用构造函数（如<xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29>和提供要序列化的其他<xref:System.Type>对象数组）（如以下代码中那样，.NET本机编译器无法解决这些类型）。  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 你必须为每个类型添加类似以下条目的条目到运行时指令文件：  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 有关示例中使用的语法的信息，请参阅[\<类型>元素](type-element-net-native.md)。  
  
## <a name="see-also"></a>另请参阅

- [运行时指令 (rd.xml) 配置文件引用](runtime-directives-rd-xml-configuration-file-reference.md)
- [运行时指令元素](runtime-directive-elements.md)
- [\<类型>元素](type-element-net-native.md)
- [\<命名空间>元素](namespace-element-net-native.md)
