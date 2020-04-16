---
title: x:FactoryMethod 指令
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432784"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="fd920-102">x:FactoryMethod 指令</span><span class="sxs-lookup"><span data-stu-id="fd920-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="fd920-103">指定 XAML 处理器应在解析对象支持类型后使用来初始化对象的构造函数以外的方法。</span><span class="sxs-lookup"><span data-stu-id="fd920-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="fd920-104">XAML 属性用法，无 x：参数</span><span class="sxs-lookup"><span data-stu-id="fd920-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="fd920-105">XAML 属性用法，x：参数作为元素</span><span class="sxs-lookup"><span data-stu-id="fd920-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="fd920-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="fd920-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="fd920-107">XAML 处理器调用的方法的字符串方法名称，用于初始化指定为`object`的实例。</span><span class="sxs-lookup"><span data-stu-id="fd920-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="fd920-108">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="fd920-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="fd920-109">指定工厂方法参数的对象的一个或多个对象元素。</span><span class="sxs-lookup"><span data-stu-id="fd920-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="fd920-110">订单很重要;它表示参数应传递给工厂方法的顺序。</span><span class="sxs-lookup"><span data-stu-id="fd920-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd920-111">备注</span><span class="sxs-lookup"><span data-stu-id="fd920-111">Remarks</span></span>  
 <span data-ttu-id="fd920-112">如果是`methodname`实例方法，则无法限定它。</span><span class="sxs-lookup"><span data-stu-id="fd920-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="fd920-113">支持作为工厂方法的静态方法。</span><span class="sxs-lookup"><span data-stu-id="fd920-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="fd920-114">如果是`methodname`静态方法，`methodname`则作为`typeName.methodName`组合提供，其中`typeName`命名定义静态工厂方法的类。</span><span class="sxs-lookup"><span data-stu-id="fd920-114">If `methodname` is a static method, `methodname` is provided as a `typeName.methodName` combination, where `typeName` names the class that defines the static factory method.</span></span> <span data-ttu-id="fd920-115">`typeName`如果引用映射的 xmlns 中的类型，则可以在前缀限定。</span><span class="sxs-lookup"><span data-stu-id="fd920-115">`typeName` can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="fd920-116">`typeName`可以是与`typeof(object)`不同的类型。</span><span class="sxs-lookup"><span data-stu-id="fd920-116">`typeName` can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="fd920-117">工厂方法必须是支持相关对象元素的类型声明的公共方法。</span><span class="sxs-lookup"><span data-stu-id="fd920-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="fd920-118">工厂方法必须返回可分配给相关对象的实例。</span><span class="sxs-lookup"><span data-stu-id="fd920-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="fd920-119">工厂方法绝不应返回 null。</span><span class="sxs-lookup"><span data-stu-id="fd920-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="fd920-120">`x:Arguments`操作的原则是最佳匹配工厂方法的签名。</span><span class="sxs-lookup"><span data-stu-id="fd920-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="fd920-121">匹配首先计算参数计数。</span><span class="sxs-lookup"><span data-stu-id="fd920-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="fd920-122">如果参数计数有多个可能的匹配项，则计算参数类型并确定最佳匹配。</span><span class="sxs-lookup"><span data-stu-id="fd920-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="fd920-123">如果在此评估阶段之后仍有歧义，则未定义 XAML 处理器行为。</span><span class="sxs-lookup"><span data-stu-id="fd920-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="fd920-124">元素`x:FactoryMethod`用法在典型意义上不是属性元素用法，因为指令标记不引用包含对象元素的类型。</span><span class="sxs-lookup"><span data-stu-id="fd920-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="fd920-125">预计元素使用比属性用法少。</span><span class="sxs-lookup"><span data-stu-id="fd920-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="fd920-126">`x:Arguments`（属性或元素用法）可以随元素使用一`x:FactoryMethod`起使用，但"使用"部分没有具体显示。</span><span class="sxs-lookup"><span data-stu-id="fd920-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="fd920-127">`x:FactoryMethod`作为元素必须位于任何其他属性元素之前，必须位于任何`x:Arguments`也作为元素提供的元素之前，并且必须位于任何内容/内部文本/初始化文本之前。</span><span class="sxs-lookup"><span data-stu-id="fd920-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd920-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd920-128">See also</span></span>

- [<span data-ttu-id="fd920-129">x:Arguments 指令</span><span class="sxs-lookup"><span data-stu-id="fd920-129">x:Arguments Directive</span></span>](xarguments-directive.md)
