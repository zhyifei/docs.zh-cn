---
title: 反射 (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: 4dfd9391407fec4bd20ac4ae05162763e909d665
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841311"
---
# <a name="reflection-c"></a><span data-ttu-id="a9351-102">反射 (C#)</span><span class="sxs-lookup"><span data-stu-id="a9351-102">Reflection (C#)</span></span>
<span data-ttu-id="a9351-103">反射提供描述程序集、模块和类型的对象（<xref:System.Type> 类型）。</span><span class="sxs-lookup"><span data-stu-id="a9351-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="a9351-104">可以使用反射动态地创建类型的实例，将类型绑定到现有对象，或从现有对象中获取类型，然后调用其方法或访问其字段和属性。</span><span class="sxs-lookup"><span data-stu-id="a9351-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="a9351-105">如果代码中使用了特性，可以利用反射来访问它们。</span><span class="sxs-lookup"><span data-stu-id="a9351-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="a9351-106">有关更多信息，请参阅[特性](../../../../docs/standard/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a9351-106">For more information, see [Attributes](../../../../docs/standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="a9351-107">下面一个简单的反射示例，使用静态方法 `GetType`被 `Object` 基类的所有类型继承）以获取变量类型：</span><span class="sxs-lookup"><span data-stu-id="a9351-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 <span data-ttu-id="a9351-108">输出为：</span><span class="sxs-lookup"><span data-stu-id="a9351-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="a9351-109">下面的示例使用反射获取已加载的程序集的完整名称。</span><span class="sxs-lookup"><span data-stu-id="a9351-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```csharp  
// Using Reflection to get information of an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 <span data-ttu-id="a9351-110">输出为：</span><span class="sxs-lookup"><span data-stu-id="a9351-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  <span data-ttu-id="a9351-111">C# 关键字 `protected` 和 `internal` 在 IL 中没有任何意义，且不会用于反射 API 中。</span><span class="sxs-lookup"><span data-stu-id="a9351-111">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="a9351-112">在 IL 中对应的术语为“系列”和“程序集”。</span><span class="sxs-lookup"><span data-stu-id="a9351-112">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="a9351-113">若要标识 `internal` 使用反射的方法，请使用 <xref:System.Reflection.MethodBase.IsAssembly%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a9351-113">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="a9351-114">若要标识 `protected internal` 方法，请使用 <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>。</span><span class="sxs-lookup"><span data-stu-id="a9351-114">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>  
  
## <a name="reflection-overview"></a><span data-ttu-id="a9351-115">反射概述</span><span class="sxs-lookup"><span data-stu-id="a9351-115">Reflection Overview</span></span>  
 <span data-ttu-id="a9351-116">反射在以下情况下很有用：</span><span class="sxs-lookup"><span data-stu-id="a9351-116">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="a9351-117">需要访问程序元数据中的特性时。</span><span class="sxs-lookup"><span data-stu-id="a9351-117">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="a9351-118">有关详细信息，请参阅[检索存储在特性中的信息](../../../standard/attributes/retrieving-information-stored-in-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="a9351-118">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="a9351-119">检查和实例化程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="a9351-119">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="a9351-120">在运行时构建新类型。</span><span class="sxs-lookup"><span data-stu-id="a9351-120">For building new types at runtime.</span></span> <span data-ttu-id="a9351-121">使用 <xref:System.Reflection.Emit> 中的类。</span><span class="sxs-lookup"><span data-stu-id="a9351-121">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="a9351-122">执行后期绑定，访问在运行时创建的类型上的方法。</span><span class="sxs-lookup"><span data-stu-id="a9351-122">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="a9351-123">请参阅主题 [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md)（动态加载和使用类型）。</span><span class="sxs-lookup"><span data-stu-id="a9351-123">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a9351-124">相关章节</span><span class="sxs-lookup"><span data-stu-id="a9351-124">Related Sections</span></span>  
 <span data-ttu-id="a9351-125">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="a9351-125">For more information:</span></span>  
  
-   [<span data-ttu-id="a9351-126">反射</span><span class="sxs-lookup"><span data-stu-id="a9351-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="a9351-127">查看类型信息</span><span class="sxs-lookup"><span data-stu-id="a9351-127">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="a9351-128">反射类型和泛型类型</span><span class="sxs-lookup"><span data-stu-id="a9351-128">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="a9351-129">检索存储在特性中的信息</span><span class="sxs-lookup"><span data-stu-id="a9351-129">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9351-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9351-130">See also</span></span>

- [<span data-ttu-id="a9351-131">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a9351-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- <span data-ttu-id="a9351-132">[Assemblies in the Common Language Runtime](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="a9351-132">[Assemblies in the Common Language Runtime](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>
