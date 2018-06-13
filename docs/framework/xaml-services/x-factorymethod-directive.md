---
title: x:FactoryMethod 指令
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 75225e624abdd3dc0862a04fae409da48b3f0d1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563410"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="a53c6-102">x:FactoryMethod 指令</span><span class="sxs-lookup"><span data-stu-id="a53c6-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="a53c6-103">指定 XAML 处理器应使用解决其后备类型后初始化对象构造函数以外的方法。</span><span class="sxs-lookup"><span data-stu-id="a53c6-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="a53c6-104">XAML 属性用法，没有 x： 自变量</span><span class="sxs-lookup"><span data-stu-id="a53c6-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="a53c6-105">XAML 属性用法，作为元素的 x： 自变量</span><span class="sxs-lookup"><span data-stu-id="a53c6-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a53c6-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="a53c6-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="a53c6-107">XAML 处理器调用以初始化为指定的实例方法的字符串方法名称`object`。</span><span class="sxs-lookup"><span data-stu-id="a53c6-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="a53c6-108">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="a53c6-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="a53c6-109">指定工厂方法参数的对象的一个或多个对象元素。</span><span class="sxs-lookup"><span data-stu-id="a53c6-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="a53c6-110">顺序很重要;它表示应在其中到工厂方法中传递自变量的顺序。</span><span class="sxs-lookup"><span data-stu-id="a53c6-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a53c6-111">备注</span><span class="sxs-lookup"><span data-stu-id="a53c6-111">Remarks</span></span>  
 <span data-ttu-id="a53c6-112">如果`methodname`是实例方法，它不能限定。</span><span class="sxs-lookup"><span data-stu-id="a53c6-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="a53c6-113">支持为工厂方法的静态方法。</span><span class="sxs-lookup"><span data-stu-id="a53c6-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="a53c6-114">如果`methodname`是静态方法，`methodname`作为提供*typeName*。*methodName*组合，其中*typeName*命名定义的静态工厂方法的类。</span><span class="sxs-lookup"><span data-stu-id="a53c6-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="a53c6-115">*typeName*可以由前缀限定如果指向映射 xmlns 中的类型。</span><span class="sxs-lookup"><span data-stu-id="a53c6-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="a53c6-116">*typeName*可以与不同的类型`typeof(``object``)`。</span><span class="sxs-lookup"><span data-stu-id="a53c6-116">*typeName* can be a different type than `typeof(``object``)`.</span></span>  
  
 <span data-ttu-id="a53c6-117">工厂方法必须是类型的支持相关对象元素的声明的公共方法。</span><span class="sxs-lookup"><span data-stu-id="a53c6-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="a53c6-118">工厂方法必须返回可分配给相关对象的实例。</span><span class="sxs-lookup"><span data-stu-id="a53c6-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="a53c6-119">工厂方法应永远不会返回 null。</span><span class="sxs-lookup"><span data-stu-id="a53c6-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="a53c6-120">`x:Arguments` 工厂方法签名的最佳匹配项的原则进行操作。</span><span class="sxs-lookup"><span data-stu-id="a53c6-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="a53c6-121">首先，匹配计算的参数计数。</span><span class="sxs-lookup"><span data-stu-id="a53c6-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="a53c6-122">如果没有为参数计数的多个可能的匹配项，参数类型为则确定计算和最佳匹配。</span><span class="sxs-lookup"><span data-stu-id="a53c6-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="a53c6-123">如果没有仍不明确性评估此阶段完成之后，XAML 处理器行为不确定。</span><span class="sxs-lookup"><span data-stu-id="a53c6-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="a53c6-124">`x:FactoryMethod`元素用法不是属性元素用法在典型的意义上，因为指令标记不引用包含对象元素的类型。</span><span class="sxs-lookup"><span data-stu-id="a53c6-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="a53c6-125">它预计该元素的用法是不如特性用法不太常见。</span><span class="sxs-lookup"><span data-stu-id="a53c6-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="a53c6-126">`x:Arguments` （属性或元素使用） 可用于沿`x:FactoryMethod`元素用法，但这是不专门部分中所示使用情况。</span><span class="sxs-lookup"><span data-stu-id="a53c6-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="a53c6-127">`x:FactoryMethod` 如元素必须位于任何其他属性元素之前，必须位于任何之前`x:Arguments`还提供作为元素，以及必须前面的任何内容/内部文本/初始化文本。</span><span class="sxs-lookup"><span data-stu-id="a53c6-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53c6-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="a53c6-128">See Also</span></span>  
 [<span data-ttu-id="a53c6-129">x:Arguments 指令</span><span class="sxs-lookup"><span data-stu-id="a53c6-129">x:Arguments Directive</span></span>](../../../docs/framework/xaml-services/x-arguments-directive.md)
