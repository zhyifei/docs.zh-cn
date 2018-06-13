---
title: 依赖项属性
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 039015f895a491d8709815d6aff52eb6139d779f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576111"
---
# <a name="dependency-properties"></a><span data-ttu-id="f5b45-102">依赖项属性</span><span class="sxs-lookup"><span data-stu-id="f5b45-102">Dependency Properties</span></span>
<span data-ttu-id="f5b45-103">依赖项属性 (DP) 是将其值存储在属性存储而不是存储在类型变量 （字段），例如一个常规属性。</span><span class="sxs-lookup"><span data-stu-id="f5b45-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="f5b45-104">附加依赖项属性是一种建模为静态的 Get 和 Set 方法表示描述对象和其容器之间的关系的"属性"的依赖项属性 (例如的位置`Button`对象上`Panel`容器）。</span><span class="sxs-lookup"><span data-stu-id="f5b45-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="f5b45-105">**✓ 执行**提供的依赖项属性，如果你需要以支持诸如样式、 触发器、 数据绑定、 动画、 动态资源和继承的 WPF 功能的属性。</span><span class="sxs-lookup"><span data-stu-id="f5b45-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="f5b45-106">依赖项属性设计</span><span class="sxs-lookup"><span data-stu-id="f5b45-106">Dependency Property Design</span></span>  
 <span data-ttu-id="f5b45-107">**✓ 执行**继承<xref:System.Windows.DependencyObject>，或子类型，在实现依赖项属性之一。</span><span class="sxs-lookup"><span data-stu-id="f5b45-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="f5b45-108">类型提供一个非常有效的属性存储实现，并自动支持 WPF 数据绑定。</span><span class="sxs-lookup"><span data-stu-id="f5b45-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="f5b45-109">**✓ 执行**提供正则 CLR 属性和公共的静态只读字段，存储的实例<xref:System.Windows.DependencyProperty?displayProperty=nameWithType>每个依赖属性。</span><span class="sxs-lookup"><span data-stu-id="f5b45-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="f5b45-110">**✓ 执行**实现通过调用实例方法的依赖项属性<xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType>和<xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f5b45-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f5b45-111">**✓ 执行**通过在"属性"。 使用属性的名称来命名依赖项属性的静态字段</span><span class="sxs-lookup"><span data-stu-id="f5b45-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="f5b45-112">**X 不**在代码中显式设置的依赖项属性的默认值; 而是将它们设置在元数据中。</span><span class="sxs-lookup"><span data-stu-id="f5b45-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="f5b45-113">如果显式设置属性默认值，则你可能会阻止通过一些隐式方式，如样式设置该属性。</span><span class="sxs-lookup"><span data-stu-id="f5b45-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="f5b45-114">**X 不**将代码放在属性访问器标准 code 之外，若要访问静态字段。</span><span class="sxs-lookup"><span data-stu-id="f5b45-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="f5b45-115">代码不会执行如果通过隐式方式，如样式，设置该属性，因为样式直接使用的静态字段。</span><span class="sxs-lookup"><span data-stu-id="f5b45-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="f5b45-116">**X 不**依赖项属性用于存储安全数据。</span><span class="sxs-lookup"><span data-stu-id="f5b45-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="f5b45-117">可以公开访问甚至私有依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="f5b45-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="f5b45-118">附加依赖项属性设计</span><span class="sxs-lookup"><span data-stu-id="f5b45-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="f5b45-119">在前面部分所述的依赖项属性表示声明类型; 内部的属性例如，`Text`属性是属性的`TextButton`，其中声明它。</span><span class="sxs-lookup"><span data-stu-id="f5b45-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="f5b45-120">一种特殊的依赖项属性是附加依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="f5b45-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="f5b45-121">附加属性的一个典型示例是<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="f5b45-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f5b45-122">该属性表示按钮 （不网格的） 列位置，但它才是相关，如果按钮包含在网格中，因此它"附加"到按钮的网格。</span><span class="sxs-lookup"><span data-stu-id="f5b45-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
```  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 <span data-ttu-id="f5b45-123">附加属性的属性定义类似于主要的正则依赖项属性，只不过访问器都由静态的 Get 和 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="f5b45-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
```  
public class Grid {  
  
    public static int GetColumn(DependencyObject obj) {  
        return (int)obj.GetValue(ColumnProperty);  
    }  
  
    public static void SetColumn(DependencyObject obj, int value) {  
        obj.SetValue(ColumnProperty,value);  
    }  
  
    public static readonly DependencyProperty ColumnProperty =  
        DependencyProperty.RegisterAttached(  
            "Column",  
            typeof(int),  
            typeof(Grid)  
    );  
}  
```  
  
## <a name="dependency-property-validation"></a><span data-ttu-id="f5b45-124">依赖项属性验证</span><span class="sxs-lookup"><span data-stu-id="f5b45-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="f5b45-125">属性通常实现了称为验证。</span><span class="sxs-lookup"><span data-stu-id="f5b45-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="f5b45-126">在尝试更改属性的值时，将执行验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="f5b45-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="f5b45-127">遗憾的是依赖项属性访问器不能包含任意验证代码。</span><span class="sxs-lookup"><span data-stu-id="f5b45-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="f5b45-128">相反，依赖项属性的验证逻辑，必须在注册过程中指定。</span><span class="sxs-lookup"><span data-stu-id="f5b45-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="f5b45-129">**X 不**将依赖项属性的验证逻辑放入的属性访问器。</span><span class="sxs-lookup"><span data-stu-id="f5b45-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="f5b45-130">相反，将传递到的验证回调`DependencyProperty.Register`方法。</span><span class="sxs-lookup"><span data-stu-id="f5b45-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="f5b45-131">依赖项属性更改通知</span><span class="sxs-lookup"><span data-stu-id="f5b45-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="f5b45-132">**X 不**在依赖项属性访问器中实现更改通知逻辑。</span><span class="sxs-lookup"><span data-stu-id="f5b45-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="f5b45-133">依赖项属性具有一种内置的更改通知功能，必须通过提供更改通知回调到使用<xref:System.Windows.PropertyMetadata>。</span><span class="sxs-lookup"><span data-stu-id="f5b45-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="f5b45-134">依赖项属性值强制转换</span><span class="sxs-lookup"><span data-stu-id="f5b45-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="f5b45-135">属性存储实际修改之前，属性 setter 到给定的值修改通过 setter 时将属性强制转换。</span><span class="sxs-lookup"><span data-stu-id="f5b45-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="f5b45-136">**X 不**在依赖项属性访问器中实现强制逻辑。</span><span class="sxs-lookup"><span data-stu-id="f5b45-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="f5b45-137">依赖项属性具有内置的强制转换功能，，但它可通过提供强制回调到`PropertyMetadata`。</span><span class="sxs-lookup"><span data-stu-id="f5b45-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="f5b45-138">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="f5b45-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f5b45-139">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="f5b45-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b45-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5b45-140">See Also</span></span>  
 [<span data-ttu-id="f5b45-141">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="f5b45-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="f5b45-142">常用设计模型</span><span class="sxs-lookup"><span data-stu-id="f5b45-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
