---
title: 反射 (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711664"
---
# <a name="reflection-c"></a><span data-ttu-id="35919-102">反射 (C#)</span><span class="sxs-lookup"><span data-stu-id="35919-102">Reflection (C#)</span></span>

<span data-ttu-id="35919-103">反射提供描述程序集、模块和类型的对象（<xref:System.Type> 类型）。</span><span class="sxs-lookup"><span data-stu-id="35919-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="35919-104">可以使用反射动态地创建类型的实例，将类型绑定到现有对象，或从现有对象中获取类型，然后调用其方法或访问其字段和属性。</span><span class="sxs-lookup"><span data-stu-id="35919-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="35919-105">如果代码中使用了特性，可以利用反射来访问它们。</span><span class="sxs-lookup"><span data-stu-id="35919-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="35919-106">有关更多信息，请参阅[特性](../../../standard/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="35919-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="35919-107">下面一个简单的反射示例，使用方法 <xref:System.Object.GetType>（被 `Object` 基类的所有类型继承）以获取变量类型：</span><span class="sxs-lookup"><span data-stu-id="35919-107">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="35919-108">请确保在 .cs 文件顶部添加 `using System;` 和 `using System.Reflection;`  。</span><span class="sxs-lookup"><span data-stu-id="35919-108">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="35919-109">输出为：`System.Int32`。</span><span class="sxs-lookup"><span data-stu-id="35919-109">The output is: `System.Int32`.</span></span>

<span data-ttu-id="35919-110">下面的示例使用反射获取已加载的程序集的完整名称。</span><span class="sxs-lookup"><span data-stu-id="35919-110">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="35919-111">输出为：`System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`。</span><span class="sxs-lookup"><span data-stu-id="35919-111">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="35919-112">C# 关键字 `protected` 和 `internal` 在 IL 中没有任何意义，且不会用于反射 API 中。</span><span class="sxs-lookup"><span data-stu-id="35919-112">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="35919-113">在 IL 中对应的术语为“系列”  和“程序集”  。</span><span class="sxs-lookup"><span data-stu-id="35919-113">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="35919-114">若要标识 `internal` 使用反射的方法，请使用 <xref:System.Reflection.MethodBase.IsAssembly%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="35919-114">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="35919-115">若要标识 `protected internal` 方法，请使用 <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>。</span><span class="sxs-lookup"><span data-stu-id="35919-115">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="35919-116">反射概述</span><span class="sxs-lookup"><span data-stu-id="35919-116">Reflection overview</span></span>

<span data-ttu-id="35919-117">反射在以下情况下很有用：</span><span class="sxs-lookup"><span data-stu-id="35919-117">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="35919-118">需要访问程序元数据中的特性时。</span><span class="sxs-lookup"><span data-stu-id="35919-118">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="35919-119">有关详细信息，请参阅[检索存储在特性中的信息](../../../standard/attributes/retrieving-information-stored-in-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="35919-119">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="35919-120">检查和实例化程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="35919-120">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="35919-121">在运行时构建新类型。</span><span class="sxs-lookup"><span data-stu-id="35919-121">For building new types at runtime.</span></span> <span data-ttu-id="35919-122">使用 <xref:System.Reflection.Emit> 中的类。</span><span class="sxs-lookup"><span data-stu-id="35919-122">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="35919-123">执行后期绑定，访问在运行时创建的类型上的方法。</span><span class="sxs-lookup"><span data-stu-id="35919-123">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="35919-124">请参阅主题 “[动态加载和使用类型](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md)”。</span><span class="sxs-lookup"><span data-stu-id="35919-124">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="35919-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="35919-125">Related sections</span></span>

<span data-ttu-id="35919-126">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="35919-126">For more information:</span></span>

- [<span data-ttu-id="35919-127">反射</span><span class="sxs-lookup"><span data-stu-id="35919-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="35919-128">查看类型信息</span><span class="sxs-lookup"><span data-stu-id="35919-128">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="35919-129">反射类型和泛型类型</span><span class="sxs-lookup"><span data-stu-id="35919-129">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="35919-130">检索存储在特性中的信息</span><span class="sxs-lookup"><span data-stu-id="35919-130">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="35919-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="35919-131">See also</span></span>

- [<span data-ttu-id="35919-132">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="35919-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="35919-133">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="35919-133">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
