---
title: 依赖项属性
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75c83dc75d1c86c89169fcc54220ced2a195bfbe
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43866853"
---
# <a name="dependency-properties"></a><span data-ttu-id="67a13-102">依赖项属性</span><span class="sxs-lookup"><span data-stu-id="67a13-102">Dependency Properties</span></span>
<span data-ttu-id="67a13-103">依赖项属性 (DP) 是将其值存储在属性存储，而不是将其存储在类型变量 （字段），例如一个常规属性。</span><span class="sxs-lookup"><span data-stu-id="67a13-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="67a13-104">非附加依赖项属性是一种依赖关系属性建模为表示描述的对象和其容器之间的关系的"属性"的静态 Get 和 Set 方法 (例如，位置`Button`对象上`Panel`容器）。</span><span class="sxs-lookup"><span data-stu-id="67a13-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="67a13-105">**✓ DO** 提供的依赖项属性，如果你需要以支持诸如样式、 触发器、 数据绑定、 动画、 动态资源和继承的 WPF 功能的属性。</span><span class="sxs-lookup"><span data-stu-id="67a13-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="67a13-106">依赖项属性设计</span><span class="sxs-lookup"><span data-stu-id="67a13-106">Dependency Property Design</span></span>  
 <span data-ttu-id="67a13-107">**✓ DO** 继承<xref:System.Windows.DependencyObject>，或子类型，在实现依赖项属性之一。</span><span class="sxs-lookup"><span data-stu-id="67a13-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="67a13-108">类型提供了一个非常有效的属性存储实现，并且自动支持 WPF 数据绑定。</span><span class="sxs-lookup"><span data-stu-id="67a13-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="67a13-109">**✓ DO** 提供正则 CLR 属性和公共的静态只读字段，存储的实例<xref:System.Windows.DependencyProperty?displayProperty=nameWithType>每个依赖属性。</span><span class="sxs-lookup"><span data-stu-id="67a13-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="67a13-110">**✓ DO** 实现通过调用实例方法的依赖项属性<xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType>和<xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="67a13-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="67a13-111">**✓ DO** 通过在"属性"。 使用属性的名称来命名依赖项属性的静态字段</span><span class="sxs-lookup"><span data-stu-id="67a13-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="67a13-112">**X DO NOT** 在代码中显式设置的依赖项属性的默认值; 而是将它们设置在元数据中。</span><span class="sxs-lookup"><span data-stu-id="67a13-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="67a13-113">如果显式设置属性默认值，可能会阻止通过某些隐式的方式，如样式设置该属性。</span><span class="sxs-lookup"><span data-stu-id="67a13-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="67a13-114">**X DO NOT** 将代码放在属性访问器标准 code 之外，若要访问静态字段。</span><span class="sxs-lookup"><span data-stu-id="67a13-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="67a13-115">代码不会执行如果通过隐式的方式，如样式，设置该属性，因为样式直接使用静态字段。</span><span class="sxs-lookup"><span data-stu-id="67a13-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="67a13-116">**X DO NOT** 依赖项属性用于存储安全数据。</span><span class="sxs-lookup"><span data-stu-id="67a13-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="67a13-117">可公开访问甚至私有依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="67a13-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="67a13-118">附加依赖项属性设计</span><span class="sxs-lookup"><span data-stu-id="67a13-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="67a13-119">在上一部分中所述的依赖项属性表示内部属性的声明类型;例如，`Text`属性是属性的`TextButton`，该声明。</span><span class="sxs-lookup"><span data-stu-id="67a13-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="67a13-120">一种特殊的依赖项属性是附加依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="67a13-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="67a13-121">附加属性的一个典型示例是<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="67a13-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="67a13-122">该属性表示按钮 （不网格的） 列的位置，但它才是相关，如果按钮包含在一个网格，因此它"附加到"按钮的网格。</span><span class="sxs-lookup"><span data-stu-id="67a13-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
```xaml
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 <span data-ttu-id="67a13-123">附加属性的定义类似于主要的常规依赖关系属性，只不过访问器都是静态的 Get 和 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="67a13-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
```csharp
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
  
## <a name="dependency-property-validation"></a><span data-ttu-id="67a13-124">依赖项属性验证</span><span class="sxs-lookup"><span data-stu-id="67a13-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="67a13-125">属性通常实现所谓的验证。</span><span class="sxs-lookup"><span data-stu-id="67a13-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="67a13-126">当尝试将属性的值更改时执行验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="67a13-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="67a13-127">遗憾的是依赖项属性访问器不能包含任意验证代码。</span><span class="sxs-lookup"><span data-stu-id="67a13-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="67a13-128">相反，需要在注册过程中指定依赖项属性验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="67a13-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="67a13-129">**X DO NOT** 将依赖项属性的验证逻辑放入的属性访问器。</span><span class="sxs-lookup"><span data-stu-id="67a13-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="67a13-130">相反，传递验证回调到`DependencyProperty.Register`方法。</span><span class="sxs-lookup"><span data-stu-id="67a13-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="67a13-131">依赖项属性更改通知</span><span class="sxs-lookup"><span data-stu-id="67a13-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="67a13-132">**X DO NOT** 在依赖项属性访问器中实现更改通知逻辑。</span><span class="sxs-lookup"><span data-stu-id="67a13-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="67a13-133">依赖项属性具有一个内置更改通知功能，必须使用通过提供到的更改通知回调<xref:System.Windows.PropertyMetadata>。</span><span class="sxs-lookup"><span data-stu-id="67a13-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="67a13-134">依赖项属性值强制转换</span><span class="sxs-lookup"><span data-stu-id="67a13-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="67a13-135">属性强制转换发生时实际上修改的属性存储之前，setter 修改指定的属性 setter 的值。</span><span class="sxs-lookup"><span data-stu-id="67a13-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="67a13-136">**X DO NOT** 在依赖项属性访问器中实现强制逻辑。</span><span class="sxs-lookup"><span data-stu-id="67a13-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="67a13-137">依赖项属性具有一个内置的强制转换的功能，且可通过提供强制回调到`PropertyMetadata`。</span><span class="sxs-lookup"><span data-stu-id="67a13-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="67a13-138">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="67a13-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="67a13-139">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="67a13-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a13-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="67a13-140">See also</span></span>

- [<span data-ttu-id="67a13-141">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="67a13-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="67a13-142">常用设计模型</span><span class="sxs-lookup"><span data-stu-id="67a13-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
