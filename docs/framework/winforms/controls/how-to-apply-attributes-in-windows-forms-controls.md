---
title: 如何：应用 Windows 窗体控件中的特性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 720172e9fcb13837b527d72176a35d366d83c948
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64612826"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="24e2b-102">如何：应用 Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="24e2b-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="24e2b-103">若要开发的组件和控件的设计环境与正确交互，并在运行时正确执行，需要正确地将特性应用于类和成员。</span><span class="sxs-lookup"><span data-stu-id="24e2b-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24e2b-104">示例</span><span class="sxs-lookup"><span data-stu-id="24e2b-104">Example</span></span>  
 <span data-ttu-id="24e2b-105">下面的代码示例演示如何使用自定义控件上的多个属性。</span><span class="sxs-lookup"><span data-stu-id="24e2b-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="24e2b-106">控件演示简单的日志记录功能。</span><span class="sxs-lookup"><span data-stu-id="24e2b-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="24e2b-107">如果该控件绑定到数据源，则会显示发送中的数据源的值<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="24e2b-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="24e2b-108">如果值超过指定的值`Threshold`属性，`ThresholdExceeded`引发事件。</span><span class="sxs-lookup"><span data-stu-id="24e2b-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="24e2b-109">`AttributesDemoControl`值与记录`LogEntry`类。</span><span class="sxs-lookup"><span data-stu-id="24e2b-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="24e2b-110">`LogEntry`类是一种模板类，这意味着它参数化的类型的记录。</span><span class="sxs-lookup"><span data-stu-id="24e2b-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="24e2b-111">例如，如果`AttributesDemoControl`是类型的日志记录值`float`，则每个`LogEntry`实例进行声明和使用，如下所示。</span><span class="sxs-lookup"><span data-stu-id="24e2b-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="24e2b-112">因为`LogEntry`已参数化的任意类型，它必须使用反射来操作参数类型。</span><span class="sxs-lookup"><span data-stu-id="24e2b-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="24e2b-113">若要运行的参数类型的阈值功能`T`必须实现<xref:System.IComparable>接口。</span><span class="sxs-lookup"><span data-stu-id="24e2b-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="24e2b-114">承载的窗体`AttributesDemoControl`定期查询的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="24e2b-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="24e2b-115">每个值中打包`LogEntry`适当类型的并且添加到窗体的<xref:System.Windows.Forms.BindingSource>。</span><span class="sxs-lookup"><span data-stu-id="24e2b-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="24e2b-116">`AttributesDemoControl`通过其数据绑定接收的值，并显示中的值<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="24e2b-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="24e2b-117">第一个代码示例是`AttributesDemoControl`实现。</span><span class="sxs-lookup"><span data-stu-id="24e2b-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="24e2b-118">第二个代码示例演示如何使用的窗体`AttributesDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="24e2b-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="24e2b-119">类级别属性</span><span class="sxs-lookup"><span data-stu-id="24e2b-119">Class-level Attributes</span></span>  
 <span data-ttu-id="24e2b-120">某些属性是在类级别应用。</span><span class="sxs-lookup"><span data-stu-id="24e2b-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="24e2b-121">下面的代码示例显示了通常应用于的 Windows 窗体控件的属性。</span><span class="sxs-lookup"><span data-stu-id="24e2b-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="24e2b-122">TypeConverter 属性</span><span class="sxs-lookup"><span data-stu-id="24e2b-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="24e2b-123"><xref:System.ComponentModel.TypeConverterAttribute> 是常用的另一个类级别属性。</span><span class="sxs-lookup"><span data-stu-id="24e2b-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="24e2b-124">下面的代码示例显示了其在将成为`LogEntry`类。</span><span class="sxs-lookup"><span data-stu-id="24e2b-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="24e2b-125">此示例还演示一种实现<xref:System.ComponentModel.TypeConverter>有关`LogEntry`类型，名为`LogEntryTypeConverter`。</span><span class="sxs-lookup"><span data-stu-id="24e2b-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="24e2b-126">成员级别的属性</span><span class="sxs-lookup"><span data-stu-id="24e2b-126">Member-level Attributes</span></span>  
 <span data-ttu-id="24e2b-127">在成员级别应用某些属性。</span><span class="sxs-lookup"><span data-stu-id="24e2b-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="24e2b-128">下面的代码示例显示通常应用于 Windows 窗体控件的属性的某些属性。</span><span class="sxs-lookup"><span data-stu-id="24e2b-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="24e2b-129">AmbientValue 属性</span><span class="sxs-lookup"><span data-stu-id="24e2b-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="24e2b-130">下面的示例演示<xref:System.ComponentModel.AmbientValueAttribute>并且会显示支持与在设计环境交互的代码。</span><span class="sxs-lookup"><span data-stu-id="24e2b-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="24e2b-131">这种交互称为*环境*。</span><span class="sxs-lookup"><span data-stu-id="24e2b-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="24e2b-132">数据绑定属性</span><span class="sxs-lookup"><span data-stu-id="24e2b-132">Databinding Attributes</span></span>  
 <span data-ttu-id="24e2b-133">下面的示例演示复杂数据绑定的实现。</span><span class="sxs-lookup"><span data-stu-id="24e2b-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="24e2b-134">在类级别<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>，显示以前，指定`DataSource`和`DataMember`用于数据绑定属性。</span><span class="sxs-lookup"><span data-stu-id="24e2b-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="24e2b-135"><xref:System.ComponentModel.AttributeProviderAttribute>指定为的类型`DataSource`属性将绑定。</span><span class="sxs-lookup"><span data-stu-id="24e2b-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24e2b-136">编译代码</span><span class="sxs-lookup"><span data-stu-id="24e2b-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="24e2b-137">承载的窗体`AttributesDemoControl`需要引用`AttributesDemoControl`若要生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="24e2b-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e2b-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="24e2b-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="24e2b-139">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="24e2b-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="24e2b-140">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="24e2b-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="24e2b-141">[如何：序列化使用 DesignerSerializationVisibilityAttribute 标准类型的集合](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="24e2b-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
