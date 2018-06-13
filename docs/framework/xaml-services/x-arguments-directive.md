---
title: x:Arguments 指令
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: e0e7f380ec176e80d2422878a2e676d64985d660
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564868"
---
# <a name="xarguments-directive"></a><span data-ttu-id="26d4a-102">x:Arguments 指令</span><span class="sxs-lookup"><span data-stu-id="26d4a-102">x:Arguments Directive</span></span>
<span data-ttu-id="26d4a-103">打包构造参数为非默认构造函数的对象元素声明在 XAML 中，或为工厂方法的对象声明。</span><span class="sxs-lookup"><span data-stu-id="26d4a-103">Packages construction arguments for a non-default constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nondefault-constructor"></a><span data-ttu-id="26d4a-104">XAML 元素用法 （非默认构造函数）</span><span class="sxs-lookup"><span data-stu-id="26d4a-104">XAML Element Usage (Nondefault constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="26d4a-105">XAML 元素用法 （工厂方法）</span><span class="sxs-lookup"><span data-stu-id="26d4a-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="26d4a-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="26d4a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="26d4a-107">指定要传递到的备份非默认构造函数或工厂方法自变量的一个或多个对象元素。</span><span class="sxs-lookup"><span data-stu-id="26d4a-107">One or more object elements that specify arguments to be passed to the backing non-default constructor or factory method.</span></span><br /><br /> <span data-ttu-id="26d4a-108">典型用法就是使用对象元素中的初始化文本指定的实际自变量值。</span><span class="sxs-lookup"><span data-stu-id="26d4a-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="26d4a-109">请参阅示例部分。</span><span class="sxs-lookup"><span data-stu-id="26d4a-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="26d4a-110">元素的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="26d4a-110">The order of the elements is significant.</span></span> <span data-ttu-id="26d4a-111">顺序中的 XAML 类型必须与类型匹配，并键入后备构造函数或工厂方法重载的顺序。</span><span class="sxs-lookup"><span data-stu-id="26d4a-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="26d4a-112">应能处理任何工厂方法的名称`x:Arguments`自变量。</span><span class="sxs-lookup"><span data-stu-id="26d4a-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="26d4a-113">依赖项</span><span class="sxs-lookup"><span data-stu-id="26d4a-113">Dependencies</span></span>  
 <span data-ttu-id="26d4a-114">`x:FactoryMethod` 可以修改的作用域和行为其中`x:Arguments`适用。</span><span class="sxs-lookup"><span data-stu-id="26d4a-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="26d4a-115">如果没有`x:FactoryMethod`指定，则`x:Arguments`适用于支持的构造函数的备用 （非默认值） 签名。</span><span class="sxs-lookup"><span data-stu-id="26d4a-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="26d4a-116">如果`x:FactoryMethod`指定，则`x:Arguments`适用于命名的方法的重载。</span><span class="sxs-lookup"><span data-stu-id="26d4a-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26d4a-117">备注</span><span class="sxs-lookup"><span data-stu-id="26d4a-117">Remarks</span></span>  
 <span data-ttu-id="26d4a-118">XAML 2006 可以支持通过初始化文本的非默认初始化。</span><span class="sxs-lookup"><span data-stu-id="26d4a-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="26d4a-119">但是，实际的应用程序的初始化文本构造技术是有限的。</span><span class="sxs-lookup"><span data-stu-id="26d4a-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="26d4a-120">初始化文本视为单个文本字符串;因此，除非为自定义信息项和从字符串的自定义分隔符可以分析的构造行为定义的类型转换器它仅添加的单个参数初始化的功能。</span><span class="sxs-lookup"><span data-stu-id="26d4a-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="26d4a-121">此外，对象逻辑的文本字符串可能是给定的 XAML 分析器默认本机类型转换器处理 true 字符串以外的其他基元。</span><span class="sxs-lookup"><span data-stu-id="26d4a-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="26d4a-122">`x:Arguments` XAML 用法不是属性元素用法在典型的意义上，因为指令标记不引用包含对象元素的类型。</span><span class="sxs-lookup"><span data-stu-id="26d4a-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="26d4a-123">这种风格更像其他指令是如`x:Code`其中元素 demarks 标记应解释为不子内容的默认值的范围。</span><span class="sxs-lookup"><span data-stu-id="26d4a-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="26d4a-124">在这种情况下，每个对象元素的 XAML 类型通信自变量类型中，XAML 分析器用于确定哪个特定构造函数的工厂方法签名的信息`x:Arguments`用法正尝试进行引用。</span><span class="sxs-lookup"><span data-stu-id="26d4a-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="26d4a-125">`x:Arguments` 对象元素正在构造必须先完成任何其他属性元素、 内容、 内部文本或对象元素的初始化字符串。</span><span class="sxs-lookup"><span data-stu-id="26d4a-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="26d4a-126">中的对象元素`x:Arguments`可以包括属性和初始化字符串许可的该 XAML 类型和其后备构造函数或工厂方法。</span><span class="sxs-lookup"><span data-stu-id="26d4a-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="26d4a-127">对于对象或自变量中，你可以指定自定义 XAML 类型或 XAML 类型，否则外部默认 XAML 命名空间是通过引用建立的前缀映射。</span><span class="sxs-lookup"><span data-stu-id="26d4a-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="26d4a-128">XAML 处理器使用以下准则来确定自变量中的指定`x:Arguments`应该用于构造一个对象。</span><span class="sxs-lookup"><span data-stu-id="26d4a-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="26d4a-129">如果`x:FactoryMethod`信息与进行比较的指定为指定`x:FactoryMethod`(请注意，值`x:FactoryMethod`是方法名称和命名的方法可以重载。</span><span class="sxs-lookup"><span data-stu-id="26d4a-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="26d4a-130">如果`x:FactoryMethod`未指定，则信息进行比较的对象的所有公共构造函数重载的集。</span><span class="sxs-lookup"><span data-stu-id="26d4a-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="26d4a-131">然后，XAML 处理逻辑比较参数的数目，并选择匹配的参数数量的重载。</span><span class="sxs-lookup"><span data-stu-id="26d4a-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="26d4a-132">如果没有匹配项不止一个，则 XAML 处理器应比较基于提供的对象元素的 XAML 类型的参数的类型。</span><span class="sxs-lookup"><span data-stu-id="26d4a-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="26d4a-133">如果没有仍多个匹配项，则 XAML 处理器行为不确定。</span><span class="sxs-lookup"><span data-stu-id="26d4a-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="26d4a-134">如果`x:FactoryMethod`指定，但该方法无法解决，XAML 处理器应引发异常。</span><span class="sxs-lookup"><span data-stu-id="26d4a-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="26d4a-135">XAML 属性用法`<x:Arguments>string</x:Arguments>`技术上可行。</span><span class="sxs-lookup"><span data-stu-id="26d4a-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="26d4a-136">但是，这提供了功能无法通过初始化文本和类型转换器，否则完成什么之外的功能，并且使用此语法不是 XAML 2009 工厂方法功能的设计意图。</span><span class="sxs-lookup"><span data-stu-id="26d4a-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="26d4a-137">示例</span><span class="sxs-lookup"><span data-stu-id="26d4a-137">Examples</span></span>  
 <span data-ttu-id="26d4a-138">下面的示例演示一个非默认构造函数签名，然后的 XAML 用法`x:Arguments`访问该签名。</span><span class="sxs-lookup"><span data-stu-id="26d4a-138">The following example shows a non-default constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
```csharp  
public class Food {  
    private string _name;  
    private Int32 _calories;  
    public Food(string name, Int32 calories) {  
        _name=name;  
        _calories=calories;  
    }  
}  
```  
  
```xaml  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 <span data-ttu-id="26d4a-139">下面的示例演示目标工厂方法签名，然后的 XAML 用法`x:Arguments`访问该签名。</span><span class="sxs-lookup"><span data-stu-id="26d4a-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
```csharp  
public Food TryLookupFood(string name)  
{  
  switch (name) {  
    case "Apple": return new Food("Apple",150);  
    case "Chocolate": return new Food("Chocolate",200);  
    case "Cheese": return new Food("Cheese", 450);  
    default: {return new Food(name,0);  
  }  
}  
```  
  
```xaml  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## <a name="see-also"></a><span data-ttu-id="26d4a-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="26d4a-140">See Also</span></span>  
 [<span data-ttu-id="26d4a-141">定义与 .NET Framework XAML 服务一起使用的自定义类型</span><span class="sxs-lookup"><span data-stu-id="26d4a-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)  
 [<span data-ttu-id="26d4a-142">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="26d4a-142">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
