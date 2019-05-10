---
title: 利用反射的 API
ms.date: 03/30/2017
ms.assetid: f9532629-6594-4a41-909f-d083f30a42f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a32e12b593f273c8b812390306c81b311da7c2a4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624700"
---
# <a name="apis-that-rely-on-reflection"></a><span data-ttu-id="f6a45-102">利用反射的 API</span><span class="sxs-lookup"><span data-stu-id="f6a45-102">APIs That Rely on Reflection</span></span>
<span data-ttu-id="f6a45-103">在某些情况下，在代码中对反射的使用不是明显的，并且 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 工具链并不保存在运行时间需要的元数据。</span><span class="sxs-lookup"><span data-stu-id="f6a45-103">In some cases, the use of reflection in code isn't obvious, and so the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain doesn't preserve metadata that is needed at run time.</span></span> <span data-ttu-id="f6a45-104">该主题介绍了一些常见的 API 或常见编程模式，它们不被视为是反射 API 的一部分，而依赖反射成功执行。</span><span class="sxs-lookup"><span data-stu-id="f6a45-104">This topic covers some common APIs or common programming patterns that aren't considered part of the reflection API but that rely on reflection to execute successfully.</span></span> <span data-ttu-id="f6a45-105">如果在源代码中使用了它们，可以将有关它们的信息添加到运行时指令 (.rd.xml) 文件，以便对这些 API 的调用不会在运行时内引发 [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 异常或某种其他异常。</span><span class="sxs-lookup"><span data-stu-id="f6a45-105">If you use them in your source code, you can add information about them to the runtime directives (.rd.xml) file so that calls to these APIs do not throw a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception or some other exception at run time.</span></span>  
  
## <a name="typemakegenerictype-method"></a><span data-ttu-id="f6a45-106">Type.MakeGenericType 方法</span><span class="sxs-lookup"><span data-stu-id="f6a45-106">Type.MakeGenericType method</span></span>  
 <span data-ttu-id="f6a45-107">你可以通过使用以下所示代码调用 `AppClass<T>` 方法来动态实例化一个泛型类型 <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>：</span><span class="sxs-lookup"><span data-stu-id="f6a45-107">You can dynamically instantiate a generic type `AppClass<T>` by calling the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method by using code like this:</span></span>  
  
 [!code-csharp[ProjectN#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/type_makegenerictype1.cs#1)]  
  
 <span data-ttu-id="f6a45-108">为使此代码在运行时间能正确运行，需要元数据的几个项。</span><span class="sxs-lookup"><span data-stu-id="f6a45-108">For this code to succeed at run time, several items of metadata are required.</span></span> <span data-ttu-id="f6a45-109">首先是未得到实例化的泛型类型 `Browse` 的 `AppClass<T>` 元数据：</span><span class="sxs-lookup"><span data-stu-id="f6a45-109">The first is `Browse` metadata for the uninstantiated generic type, `AppClass<T>`:</span></span>  
  
```xml  
<Type Name="App1.AppClass`1" Browse="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="f6a45-110">这允许 <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> 方法调用成功并返回一个有效的 <xref:System.Type> 对象。</span><span class="sxs-lookup"><span data-stu-id="f6a45-110">This allows the <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> method call to succeed and return a valid <xref:System.Type> object.</span></span>  
  
 <span data-ttu-id="f6a45-111">但即使当你为未实例化的泛型类型添加元数据时，调用 <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> 方法也会引发 [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 异常：</span><span class="sxs-lookup"><span data-stu-id="f6a45-111">But even when you add metadata for the uninstantiated generic type, calling the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method throws a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception:</span></span>  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.AppClass`1<System.Int32>.  
```  
  
 <span data-ttu-id="f6a45-112">你可以将以下运行时指令添加到运行时指令文件，从而为 `Activate` 的位于 `AppClass<T>` 上的特定实例化添加 <xref:System.Int32?displayProperty=nameWithType> 元数据。</span><span class="sxs-lookup"><span data-stu-id="f6a45-112">You can add the following run-time directive to the runtime directives file to add `Activate` metadata for the specific instantiation over `AppClass<T>` of <xref:System.Int32?displayProperty=nameWithType>:</span></span>  
  
```xml  
<TypeInstantiation Name="App1.AppClass" Arguments="System.Int32"   
                   Activate="Required Public" />  
```  
  
 <span data-ttu-id="f6a45-113">`AppClass<T>` 上的每个不同的实例化都要求一个不同的指令（如果该实例化是使用 <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> 方法创建的并且不静态使用）。</span><span class="sxs-lookup"><span data-stu-id="f6a45-113">Each different instantiation over `AppClass<T>` requires a separate directive if it is being created with the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method and not used statically.</span></span>  
  
## <a name="methodinfomakegenericmethod-method"></a><span data-ttu-id="f6a45-114">MethodInfo.MakeGenericMethod 方法</span><span class="sxs-lookup"><span data-stu-id="f6a45-114">MethodInfo.MakeGenericMethod method</span></span>  
 <span data-ttu-id="f6a45-115">给定一个含有泛型方法 `Class1` 的类 `GetMethod<T>(T t)`，`GetMethod` 可以使用类似以下所示的代码通过反射得到调用：</span><span class="sxs-lookup"><span data-stu-id="f6a45-115">Given a class `Class1` with a generic method `GetMethod<T>(T t)`, `GetMethod` can be invoked through reflection by using code like this:</span></span>  
  
 [!code-csharp[ProjectN#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/makegenericmethod1.cs#2)]  
  
 <span data-ttu-id="f6a45-116">要成功运行，此代码需要几个元数据项：</span><span class="sxs-lookup"><span data-stu-id="f6a45-116">To run successfully, this code requires several items of metadata:</span></span>  
  
- <span data-ttu-id="f6a45-117">你想要调用的方法的类型的 `Browse` 元数据。</span><span class="sxs-lookup"><span data-stu-id="f6a45-117">`Browse` metadata for the type whose method you want to call.</span></span>  
  
- <span data-ttu-id="f6a45-118">你想要调用的方法 `Browse` 元数据。</span><span class="sxs-lookup"><span data-stu-id="f6a45-118">`Browse` metadata for the method you want to call.</span></span>  <span data-ttu-id="f6a45-119">如果它是一个公共方法，为包含类型添加的公共 `Browse` 元数据也包括方法。</span><span class="sxs-lookup"><span data-stu-id="f6a45-119">If it is a public method, adding public `Browse` metadata for the containing type includes the method, too.</span></span>  
  
- <span data-ttu-id="f6a45-120">你想要调用的方法的动态元数据，保证反射调用委托不会遭到 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 工具链的删除。</span><span class="sxs-lookup"><span data-stu-id="f6a45-120">Dynamic metadata for the method you want to call, so that the reflection invocation delegate is not removed by the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain.</span></span> <span data-ttu-id="f6a45-121">如果该方法的动态元数据丢失，当 <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> 方法得到调用时会引发以下异常：</span><span class="sxs-lookup"><span data-stu-id="f6a45-121">If dynamic metadata is missing for the method, the following exception is thrown when the <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> method is called:</span></span>  
  
    ```  
    MakeGenericMethod() cannot create this generic method instantiation because the instantiation was not metadata-enabled: 'App1.Class1.GenMethod<Int32>(Int32)'.  
    ```  
  
 <span data-ttu-id="f6a45-122">以下运行时指令能确保各种所需的元数据都可用：</span><span class="sxs-lookup"><span data-stu-id="f6a45-122">The following runtime directives ensure that all required metadata is available:</span></span>  
  
```xml  
<Type Name="App1.Class1" Browse="Required PublicAndInternal">  
   <MethodInstantiation Name="GenMethod" Arguments="System.Int32" Dynamic="Required"/>  
</Type>  
```  
  
 <span data-ttu-id="f6a45-123">遭到动态调用的方法的每个不同实例化都需要一个 `MethodInstantiation` 指令，并且 `Arguments` 元素会得到更新以反射每个不同的实例化参数。</span><span class="sxs-lookup"><span data-stu-id="f6a45-123">A `MethodInstantiation` directive is required for each different instantiation of the method that is dynamically invoked, and the `Arguments` element is updated to reflect each different instantiation argument.</span></span>  
  
## <a name="arraycreateinstance-and-typemaketypearray-methods"></a><span data-ttu-id="f6a45-124">Array.CreateInstance 和 Type.MakeTypeArray 方法</span><span class="sxs-lookup"><span data-stu-id="f6a45-124">Array.CreateInstance and Type.MakeTypeArray methods</span></span>  
 <span data-ttu-id="f6a45-125">以下实例在 <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> 类型上调用了 <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> 和 `Class1` 方法。</span><span class="sxs-lookup"><span data-stu-id="f6a45-125">The following example calls the <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> methods on a type, `Class1`.</span></span>  
  
 [!code-csharp[ProjectN#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/array1.cs#3)]  
  
 <span data-ttu-id="f6a45-126">如果不存在数组元数据，以下错误会导致：</span><span class="sxs-lookup"><span data-stu-id="f6a45-126">If no array metadata is present, the following error results:</span></span>  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.Class1[]  
  
Unfortunately, no further information is available.  
```  
  
 <span data-ttu-id="f6a45-127">需要数组类型的 `Browse` 元数据才能将其动态实例化。</span><span class="sxs-lookup"><span data-stu-id="f6a45-127">`Browse` metadata for the array type is required to dynamically instantiate it.</span></span>  <span data-ttu-id="f6a45-128">以下运行时指令允许对 `Class1[]` 的进行动态实例化。</span><span class="sxs-lookup"><span data-stu-id="f6a45-128">The following runtime directive allows dynamic instantiation of `Class1[]`.</span></span>  
  
```xml  
<Type Name="App1.Class1[]" Browse="Required Public" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6a45-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6a45-129">See also</span></span>

- [<span data-ttu-id="f6a45-130">入门</span><span class="sxs-lookup"><span data-stu-id="f6a45-130">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)
- [<span data-ttu-id="f6a45-131">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="f6a45-131">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
