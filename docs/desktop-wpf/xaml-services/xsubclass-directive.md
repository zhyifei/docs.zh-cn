---
title: x:Subclass 指令
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: e85e0fb5a0e1a865ed84a93767f8152a115bbe5f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432640"
---
# <a name="xsubclass-directive"></a><span data-ttu-id="241fa-102">x:Subclass 指令</span><span class="sxs-lookup"><span data-stu-id="241fa-102">x:Subclass Directive</span></span>

<span data-ttu-id="241fa-103">在提供时`x:Class`修改 XAML 标记编译行为。</span><span class="sxs-lookup"><span data-stu-id="241fa-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="241fa-104">提供的派生类应基于`x:Class``x:Class``x:Class`，而不是创建基于 的部分类。</span><span class="sxs-lookup"><span data-stu-id="241fa-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="241fa-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="241fa-105">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="241fa-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="241fa-106">XAML Values</span></span>

|||
|-|-|
|`namespace`|<span data-ttu-id="241fa-107">可选。</span><span class="sxs-lookup"><span data-stu-id="241fa-107">Optional.</span></span> <span data-ttu-id="241fa-108">指定包含 的`classname`CLR 命名空间。</span><span class="sxs-lookup"><span data-stu-id="241fa-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="241fa-109">如果`namespace`指定，点 （.） 将分隔`namespace`和`classname`。</span><span class="sxs-lookup"><span data-stu-id="241fa-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|
|`classname`|<span data-ttu-id="241fa-110">必需。</span><span class="sxs-lookup"><span data-stu-id="241fa-110">Required.</span></span> <span data-ttu-id="241fa-111">指定连接加载的 XAML 和该 XAML 的代码后面的部分类的 CLR 名称。</span><span class="sxs-lookup"><span data-stu-id="241fa-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="241fa-112">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="241fa-112">See Remarks.</span></span>|
|`subclassNamespace`|<span data-ttu-id="241fa-113">可选。</span><span class="sxs-lookup"><span data-stu-id="241fa-113">Optional.</span></span> <span data-ttu-id="241fa-114">可以不同于`namespace`如果每个命名空间可以解析另一个。</span><span class="sxs-lookup"><span data-stu-id="241fa-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="241fa-115">指定包含 的`subclassName`CLR 命名空间。</span><span class="sxs-lookup"><span data-stu-id="241fa-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="241fa-116">如果`subclassName`指定，点 （.） 将分隔`subclassNamespace`和`subclassName`。</span><span class="sxs-lookup"><span data-stu-id="241fa-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|
|`subclassName`|<span data-ttu-id="241fa-117">必需。</span><span class="sxs-lookup"><span data-stu-id="241fa-117">Required.</span></span> <span data-ttu-id="241fa-118">指定子类的 CLR 名称。</span><span class="sxs-lookup"><span data-stu-id="241fa-118">Specifies the CLR name of the subclass.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="241fa-119">依赖项</span><span class="sxs-lookup"><span data-stu-id="241fa-119">Dependencies</span></span>

<span data-ttu-id="241fa-120">[x：类指令](xclass-directive.md)也必须在同一对象上提供，并且该对象必须是 XAML 生产的根元素。</span><span class="sxs-lookup"><span data-stu-id="241fa-120">[x:Class Directive](xclass-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>

## <a name="remarks"></a><span data-ttu-id="241fa-121">备注</span><span class="sxs-lookup"><span data-stu-id="241fa-121">Remarks</span></span>

<span data-ttu-id="241fa-122">`x:Subclass`主要用于不支持部分类声明的语言。</span><span class="sxs-lookup"><span data-stu-id="241fa-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>

<span data-ttu-id="241fa-123">用作 的`x:Subclass`类不能是嵌套类，并且必须`x:Subclass`引用根对象，如"依赖"部分中所述。</span><span class="sxs-lookup"><span data-stu-id="241fa-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>

<span data-ttu-id="241fa-124">否则，.NET XAML 服务实现未定义 其`x:Subclass`概念含义。</span><span class="sxs-lookup"><span data-stu-id="241fa-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET XAML Services implementation.</span></span> <span data-ttu-id="241fa-125">这是因为 .NET XAML 服务行为未指定连接 XAML 标记和背码的总体编程模型。</span><span class="sxs-lookup"><span data-stu-id="241fa-125">This is because .NET XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="241fa-126">与`x:Class`和`x:Subclass`相关的其他概念的实现由使用编程模型或应用程序模型来定义如何连接 XAML 标记、编译标记和基于 CLR 的代码后面的特定框架执行。</span><span class="sxs-lookup"><span data-stu-id="241fa-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="241fa-127">每个框架可能都有自己的生成操作，这些操作启用某些行为或必须包含在生成环境中的特定组件。</span><span class="sxs-lookup"><span data-stu-id="241fa-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="241fa-128">在框架中，生成操作还可以根据用于代码后面的特定 CLR 语言而变化。</span><span class="sxs-lookup"><span data-stu-id="241fa-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="241fa-129">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="241fa-129">WPF Usage Notes</span></span>

<span data-ttu-id="241fa-130">`x:Subclass`可以位于页面根上或应用程序定义中的<xref:System.Windows.Application>根上，该定义已具有`x:Class`。</span><span class="sxs-lookup"><span data-stu-id="241fa-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="241fa-131">在`x:Subclass`页面或应用程序根以外的任何元素上声明，或在不存在`x:Class`时指定它，会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="241fa-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>

<span data-ttu-id="241fa-132">创建正确适用于该方案的`x:Subclass`派生类相当复杂。</span><span class="sxs-lookup"><span data-stu-id="241fa-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="241fa-133">您可能需要检查中间文件（通过标记编译项目 obj 文件夹中生成的 .g 文件，以及包含 .xaml 文件名的名称）。</span><span class="sxs-lookup"><span data-stu-id="241fa-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="241fa-134">这些中间文件可以帮助您确定编译应用程序中联接部分类中某些编程构造的来源。</span><span class="sxs-lookup"><span data-stu-id="241fa-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>

<span data-ttu-id="241fa-135">派生类中的事件处理程序必须`internal override`（`Friend Overrides`在 Microsoft Visual Basic 中）才能覆盖在编译过程中中间类中创建的处理程序的存根。</span><span class="sxs-lookup"><span data-stu-id="241fa-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="241fa-136">否则，派生类实现将隐藏（阴影）中间类实现，并且不会调用中间类处理程序。</span><span class="sxs-lookup"><span data-stu-id="241fa-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>

<span data-ttu-id="241fa-137">定义 和`x:Class``x:Subclass`时，不需要为 引用`x:Class`的类提供任何实现。</span><span class="sxs-lookup"><span data-stu-id="241fa-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="241fa-138">您只需通过`x:Class`属性为其指定名称，以便编译器对它在中间文件中创建的类具有一些指导（在这种情况下，编译器不会选择默认名称）。</span><span class="sxs-lookup"><span data-stu-id="241fa-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="241fa-139">您可以为`x:Class`类提供一个实现;但是，这不是使用 和`x:Class``x:Subclass`的典型方案。</span><span class="sxs-lookup"><span data-stu-id="241fa-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>

## <a name="see-also"></a><span data-ttu-id="241fa-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="241fa-140">See also</span></span>

- [<span data-ttu-id="241fa-141">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="241fa-141">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="241fa-142">XAML 及 WPF 的自定义类</span><span class="sxs-lookup"><span data-stu-id="241fa-142">XAML and Custom Classes for WPF</span></span>](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
