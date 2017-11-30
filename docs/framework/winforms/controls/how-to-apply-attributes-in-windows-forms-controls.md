---
title: "如何：应用 Windows 窗体控件中的特性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4697ef7a74916bcc7b922f265262a83b8f0316d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="4aa48-102">如何：应用 Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="4aa48-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="4aa48-103">若要开发组件和控件的设计环境与正确交互，并在运行时正确执行，您需要正确将特性应用于类和成员。</span><span class="sxs-lookup"><span data-stu-id="4aa48-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4aa48-104">示例</span><span class="sxs-lookup"><span data-stu-id="4aa48-104">Example</span></span>  
 <span data-ttu-id="4aa48-105">下面的代码示例演示如何使用一个自定义控件上的多个特性。</span><span class="sxs-lookup"><span data-stu-id="4aa48-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="4aa48-106">控件演示简单的日志记录功能。</span><span class="sxs-lookup"><span data-stu-id="4aa48-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="4aa48-107">当控件绑定到数据源时，它显示发送中的数据源的值<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="4aa48-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4aa48-108">如果值超出指定的值`Threshold`属性，`ThresholdExceeded`引发事件。</span><span class="sxs-lookup"><span data-stu-id="4aa48-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="4aa48-109">`AttributesDemoControl`记录值`LogEntry`类。</span><span class="sxs-lookup"><span data-stu-id="4aa48-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="4aa48-110">`LogEntry`类是一种模板类，这意味着它参数化的类型的记录。</span><span class="sxs-lookup"><span data-stu-id="4aa48-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="4aa48-111">例如，如果`AttributesDemoControl`是类型的日志记录值`float`，每个`LogEntry`实例声明并在使用，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4aa48-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="4aa48-112">因为`LogEntry`进行参数化由任意类型，它必须使用反射来操作的参数类型。</span><span class="sxs-lookup"><span data-stu-id="4aa48-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="4aa48-113">该阈值功能起作用，参数类型的`T`必须实现<xref:System.IComparable>接口。</span><span class="sxs-lookup"><span data-stu-id="4aa48-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="4aa48-114">承载的窗体`AttributesDemoControl`定期查询性能计数器。</span><span class="sxs-lookup"><span data-stu-id="4aa48-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="4aa48-115">每个值并打包在`LogEntry`适当类型的并且添加到窗体的<xref:System.Windows.Forms.BindingSource>。</span><span class="sxs-lookup"><span data-stu-id="4aa48-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="4aa48-116">`AttributesDemoControl`通过其数据绑定接收的值并显示中的值<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="4aa48-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="4aa48-117">第一个代码示例是`AttributesDemoControl`实现。</span><span class="sxs-lookup"><span data-stu-id="4aa48-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="4aa48-118">第二个代码示例演示使用的窗体`AttributesDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="4aa48-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="4aa48-119">类级别特性</span><span class="sxs-lookup"><span data-stu-id="4aa48-119">Class-level Attributes</span></span>  
 <span data-ttu-id="4aa48-120">某些属性是在类级别应用。</span><span class="sxs-lookup"><span data-stu-id="4aa48-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="4aa48-121">下面的代码示例显示通常适用于在 Windows 窗体控件的特性。</span><span class="sxs-lookup"><span data-stu-id="4aa48-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="4aa48-122">TypeConverter 属性</span><span class="sxs-lookup"><span data-stu-id="4aa48-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="4aa48-123"><xref:System.ComponentModel.TypeConverterAttribute>是另一个常用的类级别特性。</span><span class="sxs-lookup"><span data-stu-id="4aa48-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="4aa48-124">下面的代码示例演示它的使用`LogEntry`类。</span><span class="sxs-lookup"><span data-stu-id="4aa48-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="4aa48-125">此示例还演示如何实现<xref:System.ComponentModel.TypeConverter>为`LogEntry`类型，调用`LogEntryTypeConverter`。</span><span class="sxs-lookup"><span data-stu-id="4aa48-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="4aa48-126">成员级别的属性</span><span class="sxs-lookup"><span data-stu-id="4aa48-126">Member-level Attributes</span></span>  
 <span data-ttu-id="4aa48-127">某些属性是在成员级别应用。</span><span class="sxs-lookup"><span data-stu-id="4aa48-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="4aa48-128">下面的代码示例显示某些通常应用于的 Windows 窗体控件属性的属性。</span><span class="sxs-lookup"><span data-stu-id="4aa48-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="4aa48-129">AmbientValue 属性</span><span class="sxs-lookup"><span data-stu-id="4aa48-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="4aa48-130">下面的示例演示<xref:System.ComponentModel.AmbientValueAttribute>并显示支持该产品与设计环境交互的代码。</span><span class="sxs-lookup"><span data-stu-id="4aa48-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="4aa48-131">此交互称为*环境*。</span><span class="sxs-lookup"><span data-stu-id="4aa48-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="4aa48-132">数据绑定特性</span><span class="sxs-lookup"><span data-stu-id="4aa48-132">Databinding Attributes</span></span>  
 <span data-ttu-id="4aa48-133">下面的示例演示复杂数据绑定的实现。</span><span class="sxs-lookup"><span data-stu-id="4aa48-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="4aa48-134">类级别<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>显示以前，指定`DataSource`和`DataMember`用于数据绑定属性。</span><span class="sxs-lookup"><span data-stu-id="4aa48-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="4aa48-135"><xref:System.ComponentModel.AttributeProviderAttribute>指定为的类型`DataSource`属性将绑定。</span><span class="sxs-lookup"><span data-stu-id="4aa48-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4aa48-136">编译代码</span><span class="sxs-lookup"><span data-stu-id="4aa48-136">Compiling the Code</span></span>  
  
-   <span data-ttu-id="4aa48-137">承载的窗体`AttributesDemoControl`需要引用`AttributesDemoControl`以生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="4aa48-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aa48-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4aa48-138">See Also</span></span>  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="4aa48-139">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="4aa48-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="4aa48-140">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="4aa48-140">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="4aa48-141">如何： 序列化与 DesignerSerializationVisibilityAttribute 标准类型的集合</span><span class="sxs-lookup"><span data-stu-id="4aa48-141">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
