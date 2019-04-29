---
title: 依赖项属性
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: KrzysztofCwalina
ms.openlocfilehash: 52d7a69a3f52c67ebff3f3db1daf0790e995913a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778763"
---
# <a name="dependency-properties"></a><span data-ttu-id="a9891-102">依赖项属性</span><span class="sxs-lookup"><span data-stu-id="a9891-102">Dependency Properties</span></span>
<span data-ttu-id="a9891-103">依赖项属性 (DP) 是一种常规属性，它将其值存储在属性存储中而不是其他位置（例如类型变量（字段））中。</span><span class="sxs-lookup"><span data-stu-id="a9891-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="a9891-104">附加依赖项属性是一种建模为静态 Get 和 Set 方法的依赖项属性，表示那些描述对象及其容器之间关系的“属性”（例如，`Panel` 容器中 `Button` 对象的位置）。</span><span class="sxs-lookup"><span data-stu-id="a9891-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="a9891-105">**✓ 务必**提供依赖项属性，如果需要属性 WPF 功能，例如样式、触发器、数据绑定、动画、动态资源和继承。</span><span class="sxs-lookup"><span data-stu-id="a9891-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="a9891-106">依赖项属性设计</span><span class="sxs-lookup"><span data-stu-id="a9891-106">Dependency Property Design</span></span>  
 <span data-ttu-id="a9891-107">**✓ 务必**在实现依赖属性时继承自 <xref:System.Windows.DependencyObject> 或其子类型之一。</span><span class="sxs-lookup"><span data-stu-id="a9891-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="a9891-108">该类型提供了一个非常有效的属性存储实现，并且自动支持 WPF 数据绑定。</span><span class="sxs-lookup"><span data-stu-id="a9891-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="a9891-109">**✓ 务必**提供常规 CLR 属性和公共的静态只读字段，用于存储每个依赖属性的 <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> 的实例。</span><span class="sxs-lookup"><span data-stu-id="a9891-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="a9891-110">**✓ 务必**通过调用实例方法 <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> 和 <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType> 来实现依赖属性。</span><span class="sxs-lookup"><span data-stu-id="a9891-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a9891-111">**✓ 务必** 在为依赖属性静态字段命名时以 “Property” 作为属性名称的后缀。</span><span class="sxs-lookup"><span data-stu-id="a9891-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="a9891-112">**X 切忌**在代码中显式设置依赖项属性的默认值; 而是在元数据中设置它们。</span><span class="sxs-lookup"><span data-stu-id="a9891-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="a9891-113">如果显式设置属性默认值，则可能会阻止通过某些隐式方法（例如样式）设置该属性。</span><span class="sxs-lookup"><span data-stu-id="a9891-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="a9891-114">**X 切忌**为了访问静态字段而将标准代码以外的代码放在属性访问器中。</span><span class="sxs-lookup"><span data-stu-id="a9891-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="a9891-115">如果属性是通过隐式方式（例如样式）设置的，则该代码不会执行，因为样式直接使用静态字段。</span><span class="sxs-lookup"><span data-stu-id="a9891-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="a9891-116">**X 切忌**使用依赖属性存储安全数据。</span><span class="sxs-lookup"><span data-stu-id="a9891-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="a9891-117">即使私有依赖属性也可以公开访问。</span><span class="sxs-lookup"><span data-stu-id="a9891-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="a9891-118">附加依赖项属性设计</span><span class="sxs-lookup"><span data-stu-id="a9891-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="a9891-119">上一部分中描述的依赖项属性表示声明类型的内在属性；例如，`Text` 属性是 `TextButton` 的一个属性，用来声明它。</span><span class="sxs-lookup"><span data-stu-id="a9891-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="a9891-120">一种特殊的依赖项属性是附加依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="a9891-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="a9891-121">附加属性的典型示例是 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="a9891-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a9891-122">该属性表示 Button（而不是 Grid）的列位置，但仅当 Button 包含在 Grid 中时才生效，因此它是被 Grid“附加”到 Button 的。</span><span class="sxs-lookup"><span data-stu-id="a9891-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
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
  
 <span data-ttu-id="a9891-123">附加属性的定义看起来大致类似于常规的依赖项属性，除了访问器由静态 Get 和 Set 方法表示：</span><span class="sxs-lookup"><span data-stu-id="a9891-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
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
  
## <a name="dependency-property-validation"></a><span data-ttu-id="a9891-124">依赖项属性验证</span><span class="sxs-lookup"><span data-stu-id="a9891-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="a9891-125">属性通常会实施所谓的验证。</span><span class="sxs-lookup"><span data-stu-id="a9891-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="a9891-126">尝试更改属性的值时，系统会执行验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="a9891-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="a9891-127">遗憾的是，依赖项属性访问器不能包含任意验证代码，</span><span class="sxs-lookup"><span data-stu-id="a9891-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="a9891-128">相反，只能在属性注册期间指定依赖项属性的验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="a9891-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="a9891-129">**X 切忌**将依赖属性验证逻辑放入属性访问器。</span><span class="sxs-lookup"><span data-stu-id="a9891-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="a9891-130">相反，应将验证回叫传递到 `DependencyProperty.Register` 方法。</span><span class="sxs-lookup"><span data-stu-id="a9891-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="a9891-131">依赖属性更改通知</span><span class="sxs-lookup"><span data-stu-id="a9891-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="a9891-132">**X 切忌**在依赖属性访问器中实现更改通知逻辑。</span><span class="sxs-lookup"><span data-stu-id="a9891-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="a9891-133">依赖属性具有一个内置更改通知功能，必须通过向 <xref:System.Windows.PropertyMetadata> 提供更改通知回叫才能使用该功能。</span><span class="sxs-lookup"><span data-stu-id="a9891-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="a9891-134">依赖项属性值强制转换</span><span class="sxs-lookup"><span data-stu-id="a9891-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="a9891-135">在实际修改属性存储之前，如果赋给属性 setter 的值被 setter 修改，则会发生属性强制转换。</span><span class="sxs-lookup"><span data-stu-id="a9891-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="a9891-136">**X 切忌**在依赖属性访问器中实现强制逻辑。</span><span class="sxs-lookup"><span data-stu-id="a9891-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="a9891-137">依赖项属性有一个内置的强制转换功能，可以通过向 `PropertyMetadata` 提供强制回调来使用它。</span><span class="sxs-lookup"><span data-stu-id="a9891-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="a9891-138">*部分版权 © 2005、2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="a9891-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a9891-139">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="a9891-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9891-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9891-140">See also</span></span>

- [<span data-ttu-id="a9891-141">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="a9891-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a9891-142">常用设计模型</span><span class="sxs-lookup"><span data-stu-id="a9891-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
