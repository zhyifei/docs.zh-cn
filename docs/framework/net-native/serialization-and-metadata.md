---
title: 序列化和元数据
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1ee70c2701492acd331e5faed849ff0b2e8b559
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052381"
---
# <a name="serialization-and-metadata"></a><span data-ttu-id="0d21d-102">序列化和元数据</span><span class="sxs-lookup"><span data-stu-id="0d21d-102">Serialization and Metadata</span></span>
<span data-ttu-id="0d21d-103">如果你的应用会序列化和反序列化对象，你可能需要将条目添加到运行时指令 (.rd.xml) 文件以确保必要的元数据在运行时间存在。</span><span class="sxs-lookup"><span data-stu-id="0d21d-103">If your app serializes and deserializes objects, you may need to add entries to your runtime directives (.rd.xml) file to ensure that the necessary metadata is present at run time.</span></span> <span data-ttu-id="0d21d-104">有两类序列化序列化程序，并且每一类要求在你的运行时指令文件中进行不同处理：</span><span class="sxs-lookup"><span data-stu-id="0d21d-104">There are two categories of serializers, and each requires different handling in your runtime directives file:</span></span>  
  
- <span data-ttu-id="0d21d-105">基于反射的第三方序列化程序。</span><span class="sxs-lookup"><span data-stu-id="0d21d-105">Reflection-based third-party serializers.</span></span> <span data-ttu-id="0d21d-106">这些程序要求修改你的运行时指令文件，我们会在后面一部分对其进行讨论。</span><span class="sxs-lookup"><span data-stu-id="0d21d-106">These require modifications to your runtime directives file, and are discussed in the next section.</span></span>  
  
- <span data-ttu-id="0d21d-107">在 .NET Framework 类库中找到的非基于反射的序列化程序。</span><span class="sxs-lookup"><span data-stu-id="0d21d-107">Non-reflection based serializers found in the .NET Framework class library.</span></span> <span data-ttu-id="0d21d-108">这些程序可能要求修改运行时指令文件，我们会在 [Microsoft 序列化程序](#Microsoft)部分对其进行讨论。</span><span class="sxs-lookup"><span data-stu-id="0d21d-108">These may require modifications to your runtime directives file, and are discussed in the [Microsoft serializers](#Microsoft) section.</span></span>  
  
<a name="ThirdParty"></a>   
## <a name="third-party-serializers"></a><span data-ttu-id="0d21d-109">第三方序列化程序</span><span class="sxs-lookup"><span data-stu-id="0d21d-109">Third-party serializers</span></span>  
 <span data-ttu-id="0d21d-110">Newtonsoft.JSON 等第三方序列化程序通常是基于反射的。</span><span class="sxs-lookup"><span data-stu-id="0d21d-110">Third-part serializers, including Newtonsoft.JSON, typically are reflection-based.</span></span> <span data-ttu-id="0d21d-111">考虑到一个序列化数据的二进制大型对象 (BLOB)，该数据中的字段通过按名称查找目标类型的字段被分配到了一个具体类型。</span><span class="sxs-lookup"><span data-stu-id="0d21d-111">Given a binary large object (BLOB) of serialized data, the fields in the data are assigned to a concrete type by looking up the fields of the target type by name.</span></span> <span data-ttu-id="0d21d-112">在最低限度下，使用这些库时，在 `List<Type>` 集合中尝试序列化或反序列化的每个 <xref:System.Type> 对象都会出现 [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 异常。</span><span class="sxs-lookup"><span data-stu-id="0d21d-112">At a minimum, using these libraries causes [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exceptions for each <xref:System.Type> object that you try to serialize or deserialize in a `List<Type>` collection.</span></span>  
  
 <span data-ttu-id="0d21d-113">处理由这些序列化程序的丢失元数据引起的最简单的方法是，收集将被用在单独命名空间（比如 `App.Models`）下序列化中的类型，并向其直接应用一个 `Serialize` 元数据指令：</span><span class="sxs-lookup"><span data-stu-id="0d21d-113">The easiest way to address issues caused by missing metadata for these serializers is to collect types that will be used in serialization under a single namespace (such as `App.Models`) and apply a `Serialize` metadata directive to it:</span></span>  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="0d21d-114">有关示例中所使用语法的信息，请参阅 [\<Namespace> 元素](../../../docs/framework/net-native/namespace-element-net-native.md)。</span><span class="sxs-lookup"><span data-stu-id="0d21d-114">For information about the syntax used in the example, see [\<Namespace> Element](../../../docs/framework/net-native/namespace-element-net-native.md).</span></span>  
  
<a name="Microsoft"></a>   
## <a name="microsoft-serializers"></a><span data-ttu-id="0d21d-115">Microsoft 序列化程序</span><span class="sxs-lookup"><span data-stu-id="0d21d-115">Microsoft serializers</span></span>  
 <span data-ttu-id="0d21d-116">尽管 <xref:System.Runtime.Serialization.DataContractSerializer>、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 和 <xref:System.Xml.Serialization.XmlSerializer> 类并不依赖反射，它们需要在要得到序列化或反序列化的对象的基础上生成的代码。</span><span class="sxs-lookup"><span data-stu-id="0d21d-116">Although the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes do not rely on reflection, they do require code to be generated based on the object to be serialized or deserialized.</span></span> <span data-ttu-id="0d21d-117">每个序列化程序的重载构造函数包含一个指定需要得到序列化或反序列化的 <xref:System.Type> 参数。</span><span class="sxs-lookup"><span data-stu-id="0d21d-117">The overloaded constructors for each serializer include a <xref:System.Type> parameter that specifies the type to be serialized or deserialized.</span></span> <span data-ttu-id="0d21d-118">你在代码中如何指定该类型定义了你必须进行的操作，这将在以下两部分中讨论到。</span><span class="sxs-lookup"><span data-stu-id="0d21d-118">How you specify that type in your code defines the action you must take, as discussed in the next two sections.</span></span>  
  
### <a name="typeof-used-in-the-constructor"></a><span data-ttu-id="0d21d-119">构造函数中使用的 TypeOf</span><span class="sxs-lookup"><span data-stu-id="0d21d-119">typeof used in the constructor</span></span>  
 <span data-ttu-id="0d21d-120">如果调用了这些序列化类的构造函数并在方法调用中包含了 C# [Typeof](~/docs/csharp/language-reference/keywords/typeof.md) 关键字，则不需要执行任何额外操作。</span><span class="sxs-lookup"><span data-stu-id="0d21d-120">If you call a constructor of these serialization classes and include the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword in the method call, **you do not have to do any additional work**.</span></span> <span data-ttu-id="0d21d-121">例如，在以下对序列化类构造函数的每个调用中，`typeof` 关键字被用作了传递给构造函数的表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="0d21d-121">For example, in each of the following calls to a serialization class constructor, the `typeof` keyword is used as part of the expression passed to the constructor.</span></span>  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 <span data-ttu-id="0d21d-122">.NET Native 编译器将自动处理此代码。</span><span class="sxs-lookup"><span data-stu-id="0d21d-122">The .NET Native compiler will automatically handle this code.</span></span>  
  
### <a name="typeof-used-outside-the-constructor"></a><span data-ttu-id="0d21d-123">构造函数外部使用的 TypeOf</span><span class="sxs-lookup"><span data-stu-id="0d21d-123">typeof used outside the constructor</span></span>  
 <span data-ttu-id="0d21d-124">如果你调用了这些序列化类的构造函数，并使用C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md)关键字提供给构造函数的表达式外部<xref:System.Type>参数，如以下代码所示.NET Native 编译器不能解析的类型：</span><span class="sxs-lookup"><span data-stu-id="0d21d-124">If you call a constructor of these serialization classes and use the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword outside the expression supplied to the constructor’s <xref:System.Type> parameter, as in the following code, the .NET Native compiler cannot resolve the type:</span></span>  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 <span data-ttu-id="0d21d-125">在这种情况下，你必须通过添加如下所示的条目指定在运行时指令文件中的类型：</span><span class="sxs-lookup"><span data-stu-id="0d21d-125">In this case, you must specify the type in the runtime directives file by adding an entry like this:</span></span>  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 <span data-ttu-id="0d21d-126">同样，如果您调用构造函数，如<xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>并提供了一系列其他<xref:System.Type>要序列化，如下面的代码中.NET Native 编译器无法解析这些类型的对象。</span><span class="sxs-lookup"><span data-stu-id="0d21d-126">Similarly, if you call a constructor such as <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> and provide an array of additional <xref:System.Type> objects to serialize, as in the following code, the .NET Native compiler cannot resolve these types.</span></span>  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 <span data-ttu-id="0d21d-127">你必须为每个类型添加类似以下条目的条目到运行时指令文件：</span><span class="sxs-lookup"><span data-stu-id="0d21d-127">You must add entries such as the following for each type to the runtime directives file:</span></span>  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 <span data-ttu-id="0d21d-128">有关示例中所使用语法的信息，请参阅 [\<Type> 元素](../../../docs/framework/net-native/type-element-net-native.md)。</span><span class="sxs-lookup"><span data-stu-id="0d21d-128">For information about the syntax used in the example, see [\<Type> Element](../../../docs/framework/net-native/type-element-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d21d-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d21d-129">See also</span></span>

- [<span data-ttu-id="0d21d-130">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="0d21d-130">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0d21d-131">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="0d21d-131">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="0d21d-132">\<类型 > 元素</span><span class="sxs-lookup"><span data-stu-id="0d21d-132">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)
- [<span data-ttu-id="0d21d-133">\<Namespace > 元素</span><span class="sxs-lookup"><span data-stu-id="0d21d-133">\<Namespace> Element</span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)
