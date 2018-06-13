---
title: 将自定义活动属性绑定到设计器控件
ms.date: 03/30/2017
ms.assetid: 2e8061ea-10f5-407c-a31f-d0d74ce12f27
ms.openlocfilehash: 1aa22403f5ed2de6893f8bfec9f03fa7dabd6868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513544"
---
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a><span data-ttu-id="23204-102">将自定义活动属性绑定到设计器控件</span><span class="sxs-lookup"><span data-stu-id="23204-102">Binding a custom activity property to a designer control</span></span>
<span data-ttu-id="23204-103">将文本框设计器控件与活动自变量绑定非常简单；但将复杂设计器控件（如组合框）与活动自变量绑定则可能非常困难。</span><span class="sxs-lookup"><span data-stu-id="23204-103">Binding a text box designer control to an activity argument is fairly straightforward; binding a complex designer control (such as a combo box) to an activity argument may present challenges, however.</span></span> <span data-ttu-id="23204-104">本主题讨论如何将活动参数与自定义活动设计器上的组合框控件绑定。</span><span class="sxs-lookup"><span data-stu-id="23204-104">This topic discusses how to bind an activity argument to a combo box control on a custom activity designer.</span></span>  
  
#### <a name="creating-the-combo-box-item-converter"></a><span data-ttu-id="23204-105">创建组合框项转换器</span><span class="sxs-lookup"><span data-stu-id="23204-105">Creating the combo box item converter</span></span>  
  
1.  <span data-ttu-id="23204-106">在 Visual Studio 中新建一个名为 CustomProperty 的空解决方案。</span><span class="sxs-lookup"><span data-stu-id="23204-106">Create a new empty solution in Visual Studio called CustomProperty.</span></span>  
  
2.  <span data-ttu-id="23204-107">新建一个名为 ComboBoxItemConverter 的类。</span><span class="sxs-lookup"><span data-stu-id="23204-107">Create a new class called ComboBoxItemConverter.</span></span> <span data-ttu-id="23204-108">添加对 System.Windows.Data 的引用，并让该类从 <xref:System.Windows.Data.IValueConverter> 派生。</span><span class="sxs-lookup"><span data-stu-id="23204-108">Add a reference to System.Windows.Data, and have the class derive from <xref:System.Windows.Data.IValueConverter>.</span></span> <span data-ttu-id="23204-109">让 Visual Studio 实现该接口以生成 `Convert` 和 `ConvertBack` 的存根。</span><span class="sxs-lookup"><span data-stu-id="23204-109">Have Visual Studio implement the interface to generate stubs for `Convert` and `ConvertBack`.</span></span>  
  
3.  <span data-ttu-id="23204-110">将以下代码添加到 `Convert` 方法中。</span><span class="sxs-lookup"><span data-stu-id="23204-110">Add the following code to the `Convert` method.</span></span> <span data-ttu-id="23204-111">此代码会将 <xref:System.Activities.InArgument%601> 类型的活动 <xref:System.String> 转换为要放入设计器中的值。</span><span class="sxs-lookup"><span data-stu-id="23204-111">This code converts the activity's <xref:System.Activities.InArgument%601> of type <xref:System.String> to the value to be placed in the designer.</span></span>  
  
    ```  
    ModelItem modelItem = value as ModelItem;  
    if (value != null)  
    {  
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;  
  
        if (inArgument != null)  
        {  
            Activity<string> expression = inArgument.Expression;  
            VisualBasicValue<string> vbexpression = expression as VisualBasicValue<string>;  
            Literal<string> literal = expression as Literal<string>;  
  
            if (literal != null)  
            {  
                return "\"" + literal.Value + "\"";  
            }  
            else if (vbexpression != null)  
            {  
                return vbexpression.ExpressionText;  
            }  
        }  
    }  
    return null;  
    ```  
  
     <span data-ttu-id="23204-112">还可以使用 <xref:Microsoft.CSharp.Activities.CSharpValue%601>（而不是 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>）创建上面代码段中的表达式。</span><span class="sxs-lookup"><span data-stu-id="23204-112">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>  
  
    ```  
    ModelItem modelItem = value as ModelItem;  
    if (value != null)  
    {  
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;  
  
        if (inArgument != null)  
        {  
            Activity<string> expression = inArgument.Expression;  
            CSharpValue<string> csexpression = expression as CSharpValue<string>;  
            Literal<string> literal = expression as Literal<string>;  
  
            if (literal != null)  
            {  
                return "\"" + literal.Value + "\"";  
            }  
            else if (csexpression != null)  
            {  
                return csexpression.ExpressionText;  
            }  
        }  
    }  
    return null;  
    ```  
  
4.  <span data-ttu-id="23204-113">将以下代码添加到 `ConvertBack` 方法中。</span><span class="sxs-lookup"><span data-stu-id="23204-113">Add the following code to the `ConvertBack` method.</span></span> <span data-ttu-id="23204-114">此代码会将传入的组合框项再转回为 <xref:System.Activities.InArgument%601>。</span><span class="sxs-lookup"><span data-stu-id="23204-114">This code converts the incoming combo box item back to an <xref:System.Activities.InArgument%601>.</span></span>  
  
    ```  
    // Convert combo box value to InArgument<string>  
                string itemContent = (string)((ComboBoxItem)value).Content;  
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);  
                InArgument<string> inArgument = new InArgument<string>(vbArgument);  
                return inArgument;  
    ```  
  
     <span data-ttu-id="23204-115">还可以使用 <xref:Microsoft.CSharp.Activities.CSharpValue%601>（而不是 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>）创建上面代码段中的表达式。</span><span class="sxs-lookup"><span data-stu-id="23204-115">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>  
  
    ```  
    // Convert combo box value to InArgument<string>  
                string itemContent = (string)((ComboBoxItem)value).Content;  
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);  
                InArgument<string> inArgument = new InArgument<string>(csArgument);  
                return inArgument;  
    ```  
  
#### <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a><span data-ttu-id="23204-116">向活动的自定义设计器添加 ComboBoxItemConverter</span><span class="sxs-lookup"><span data-stu-id="23204-116">Adding the ComboBoxItemConverter to the custom designer of an activity</span></span>  
  
1.  <span data-ttu-id="23204-117">向项目添加一个新项。</span><span class="sxs-lookup"><span data-stu-id="23204-117">Add a new item to the project.</span></span> <span data-ttu-id="23204-118">在“新建项”对话框中，选择“工作流”节点并选择“活动设计器”作为新项的类型。</span><span class="sxs-lookup"><span data-stu-id="23204-118">In the New Item dialog, select the Workflow node and select Activity Designer as the type of the new item.</span></span> <span data-ttu-id="23204-119">将该项命名为 CustomPropertyDesigner。</span><span class="sxs-lookup"><span data-stu-id="23204-119">Name the item CustomPropertyDesigner.</span></span>  
  
2.  <span data-ttu-id="23204-120">向新设计器添加一个组合框。</span><span class="sxs-lookup"><span data-stu-id="23204-120">Add a Combo Box to the new designer.</span></span> <span data-ttu-id="23204-121">在项属性中，向组合框添加两项，其“内容”值分别为“Item1”和“Item2”。</span><span class="sxs-lookup"><span data-stu-id="23204-121">In the Items property, add a couple of items to the combo box, with Content values of "Item1" and 'Item2".</span></span>  
  
3.  <span data-ttu-id="23204-122">修改组合框的 XAML，以将新的项转换器添加为要用于组合框的项转换器。</span><span class="sxs-lookup"><span data-stu-id="23204-122">Modify the XAML of the combo box to add the new item converter as the item converter to be used for the combo box.</span></span> <span data-ttu-id="23204-123">转换器作为资源添加到 ActivityDesigner.Resources 段中，然后在 <xref:System.Windows.Controls.ComboBox> 的 Converter 属性中指定该转换器。</span><span class="sxs-lookup"><span data-stu-id="23204-123">The converter is added as a resource in the ActivityDesigner.Resources segment, and specifies the converter in the Converter attribute for the <xref:System.Windows.Controls.ComboBox>.</span></span> <span data-ttu-id="23204-124">请注意，项目的命名空间是在活动设计器的命名空间属性中指定的；如果要将该设计器用在另一个项目中，也需要更改此命名空间。</span><span class="sxs-lookup"><span data-stu-id="23204-124">Note that the namespace of the project is specified in the namespaces attributes for the activity designer; if the designer is to be used in a different project, this namespace will need to be changed.</span></span>  
  
    ```  
    <sap:ActivityDesigner x:Class="CustomProperty.CustomPropertyDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:c="clr-namespace:CustomProperty"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
  
        <sap:ActivityDesigner.Resources>  
            <ResourceDictionary>  
                <c:ComboBoxItemConverter x:Key="comboBoxItemConverter"/>  
            </ResourceDictionary>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ComboBox SelectedValue="{Binding Path=ModelItem.Text, Mode=TwoWay, Converter={StaticResource comboBoxItemConverter}}"  Height="23" HorizontalAlignment="Left" Margin="132,5,0,0" Name="comboBox1" VerticalAlignment="Top" Width="120" ItemsSource="{Binding}">  
                <ComboBoxItem>item1</ComboBoxItem>  
                <ComboBoxItem>item2</ComboBoxItem>  
            </ComboBox>  
        </Grid>  
    </sap:ActivityDesigner>  
    ```  
  
4.  <span data-ttu-id="23204-125">新建一个 <xref:System.Activities.CodeActivity> 类型的项。</span><span class="sxs-lookup"><span data-stu-id="23204-125">Create a new item of type <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="23204-126">对本示例而言，IDE 为活动创建的默认代码就足够了。</span><span class="sxs-lookup"><span data-stu-id="23204-126">The default code created by the IDE for the activity will be sufficient for this example.</span></span>  
  
5.  <span data-ttu-id="23204-127">向类定义添加下列属性：</span><span class="sxs-lookup"><span data-stu-id="23204-127">Add the following attribute to the class definition:</span></span>  
  
    ```  
    [Designer(typeof(CustomPropertyDesigner))]  
    ```  
  
     <span data-ttu-id="23204-128">此行代码将新设计器与新类相关联。</span><span class="sxs-lookup"><span data-stu-id="23204-128">This line associates the new designer with the new class.</span></span>  
  
 <span data-ttu-id="23204-129">新活动现在应当已与设计器关联起来。</span><span class="sxs-lookup"><span data-stu-id="23204-129">The new activity should now be associated with the designer.</span></span> <span data-ttu-id="23204-130">若要测试新活动，将其添加到一个工作流中，然后将组合框设置为它的两个值。</span><span class="sxs-lookup"><span data-stu-id="23204-130">To test the new activity, add it to a workflow, and set the combo box to the two values.</span></span> <span data-ttu-id="23204-131">属性窗口将会更新以反映组合框的值。</span><span class="sxs-lookup"><span data-stu-id="23204-131">The properties window should update to reflect the combo box value.</span></span>
