---
title: 在控件中应用特性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: b8ecd516cf6bb189c6ad1b208dd8e3a5444f001c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741491"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="802ea-102">방법: Windows Forms 컨트롤에서 특성 적용</span><span class="sxs-lookup"><span data-stu-id="802ea-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="802ea-103">若要开发正确与设计环境进行交互并在运行时正确执行的组件和控件，需要正确地将特性应用于类和成员。</span><span class="sxs-lookup"><span data-stu-id="802ea-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="802ea-104">示例</span><span class="sxs-lookup"><span data-stu-id="802ea-104">Example</span></span>  
 <span data-ttu-id="802ea-105">下面的代码示例演示如何在自定义控件上使用多个特性。</span><span class="sxs-lookup"><span data-stu-id="802ea-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="802ea-106">控件说明了简单的日志记录功能。</span><span class="sxs-lookup"><span data-stu-id="802ea-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="802ea-107">当控件绑定到数据源时，它将在 <xref:System.Windows.Forms.DataGridView> 控件中显示数据源发送的值。</span><span class="sxs-lookup"><span data-stu-id="802ea-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="802ea-108">如果某个值超出 `Threshold` 属性指定的值，则会引发 `ThresholdExceeded` 事件。</span><span class="sxs-lookup"><span data-stu-id="802ea-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="802ea-109">`AttributesDemoControl` 使用 `LogEntry` 类记录值。</span><span class="sxs-lookup"><span data-stu-id="802ea-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="802ea-110">`LogEntry` 类是一个模板类，这意味着它将在它所记录的类型中进行参数化。</span><span class="sxs-lookup"><span data-stu-id="802ea-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="802ea-111">例如，如果 `AttributesDemoControl` 记录 `float`类型的值，则声明每个 `LogEntry` 实例，并按如下所示使用。</span><span class="sxs-lookup"><span data-stu-id="802ea-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="802ea-112">由于 `LogEntry` 由任意类型参数化，因此它必须使用反射来对参数类型进行操作。</span><span class="sxs-lookup"><span data-stu-id="802ea-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="802ea-113">要使阈值功能正常工作，参数类型 `T` 必须实现 <xref:System.IComparable> 接口。</span><span class="sxs-lookup"><span data-stu-id="802ea-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="802ea-114">承载 `AttributesDemoControl` 的窗体定期查询性能计数器。</span><span class="sxs-lookup"><span data-stu-id="802ea-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="802ea-115">每个值都打包在适当类型的 `LogEntry` 中并添加到窗体的 <xref:System.Windows.Forms.BindingSource>中。</span><span class="sxs-lookup"><span data-stu-id="802ea-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="802ea-116">`AttributesDemoControl` 通过数据绑定接收值并在 <xref:System.Windows.Forms.DataGridView> 控件中显示值。</span><span class="sxs-lookup"><span data-stu-id="802ea-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="802ea-117">第一个代码示例是 `AttributesDemoControl` 实现。</span><span class="sxs-lookup"><span data-stu-id="802ea-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="802ea-118">第二个代码示例演示使用 `AttributesDemoControl`的窗体。</span><span class="sxs-lookup"><span data-stu-id="802ea-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="802ea-119">类级属性</span><span class="sxs-lookup"><span data-stu-id="802ea-119">Class-level Attributes</span></span>  
 <span data-ttu-id="802ea-120">某些属性应用于类级别。</span><span class="sxs-lookup"><span data-stu-id="802ea-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="802ea-121">下面的代码示例演示通常应用于 Windows 窗体控件的特性。</span><span class="sxs-lookup"><span data-stu-id="802ea-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="802ea-122">TypeConverter 特性</span><span class="sxs-lookup"><span data-stu-id="802ea-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="802ea-123"><xref:System.ComponentModel.TypeConverterAttribute> 是另一个常用的类级属性。</span><span class="sxs-lookup"><span data-stu-id="802ea-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="802ea-124">下面的代码示例演示了如何对 `LogEntry` 类使用。</span><span class="sxs-lookup"><span data-stu-id="802ea-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="802ea-125">此示例还演示了 `LogEntry` 类型（称为 `LogEntryTypeConverter`）的 <xref:System.ComponentModel.TypeConverter> 实现。</span><span class="sxs-lookup"><span data-stu-id="802ea-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="802ea-126">成员级特性</span><span class="sxs-lookup"><span data-stu-id="802ea-126">Member-level Attributes</span></span>  
 <span data-ttu-id="802ea-127">某些属性应用于成员级别。</span><span class="sxs-lookup"><span data-stu-id="802ea-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="802ea-128">下面的代码示例演示一些通常应用于 Windows 窗体控件的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="802ea-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="802ea-129">AmbientValue 特性</span><span class="sxs-lookup"><span data-stu-id="802ea-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="802ea-130">下面的示例演示了 <xref:System.ComponentModel.AmbientValueAttribute>，并显示了支持与设计环境交互的代码。</span><span class="sxs-lookup"><span data-stu-id="802ea-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="802ea-131">这种交互称为 "*环境*"。</span><span class="sxs-lookup"><span data-stu-id="802ea-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="802ea-132">数据绑定属性</span><span class="sxs-lookup"><span data-stu-id="802ea-132">Databinding Attributes</span></span>  
 <span data-ttu-id="802ea-133">下面的示例演示如何实现复杂数据绑定。</span><span class="sxs-lookup"><span data-stu-id="802ea-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="802ea-134">上面所示的类级别 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>指定了用于数据绑定的 `DataSource` 和 `DataMember` 属性。</span><span class="sxs-lookup"><span data-stu-id="802ea-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="802ea-135"><xref:System.ComponentModel.AttributeProviderAttribute> 指定 `DataSource` 属性将绑定到的类型。</span><span class="sxs-lookup"><span data-stu-id="802ea-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="802ea-136">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="802ea-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="802ea-137">承载 `AttributesDemoControl` 的窗体需要引用 `AttributesDemoControl` 的程序集才能生成。</span><span class="sxs-lookup"><span data-stu-id="802ea-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="802ea-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="802ea-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="802ea-139">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="802ea-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="802ea-140">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="802ea-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="802ea-141">[如何：用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="802ea-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
