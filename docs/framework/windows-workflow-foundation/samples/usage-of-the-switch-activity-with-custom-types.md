---
title: 带自定义类型的切换活动的用法
ms.date: 03/30/2017
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
ms.openlocfilehash: b24a03573b31f3fb1c34d4aa6e03bc11f5b25455
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44038869"
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a><span data-ttu-id="fd5b5-102">带自定义类型的切换活动的用法</span><span class="sxs-lookup"><span data-stu-id="fd5b5-102">Usage of the Switch Activity with Custom Types</span></span>
<span data-ttu-id="fd5b5-103">此示例介绍如何使 <xref:System.Activities.Statements.Switch%601> 活动能够在运行时计算用户定义的复杂类型。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-103">This sample describes how to enable a <xref:System.Activities.Statements.Switch%601> activity to evaluate a user-defined complex type at runtime.</span></span> <span data-ttu-id="fd5b5-104">在大多数传统的过程性编程语言，[切换](https://go.microsoft.com/fwlink/?LinkId=180521)语句选择执行逻辑基于变量的条件评估。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-104">In most traditional procedural programming languages, a [switch](https://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable.</span></span> <span data-ttu-id="fd5b5-105">传统上，`switch` 语句会操作可静态计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-105">Traditionally, a `switch` statement operates on an expression that can be statically evaluated.</span></span> <span data-ttu-id="fd5b5-106">例如，在 C# 中，这表示仅支持基元类型（如 <xref:System.Boolean>、<xref:System.Int32>、<xref:System.String>）和枚举类型。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-106">For example, in C# this means that only primitive types, such as <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, and enumeration types are supported.</span></span>  
  
 <span data-ttu-id="fd5b5-107">若要启用针对自定义类的切换，则必须实现逻辑以在运行时计算自定义复杂类型的值。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-107">To enable switching on a custom class, logic must be implemented to evaluate values of the custom complex type at runtime.</span></span> <span data-ttu-id="fd5b5-108">此示例演示如何启用针对名为 `Person` 的自定义复杂类型的切换。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-108">This sample demonstrates how to enable switching on a custom complex type named `Person`.</span></span>  
  
-   <span data-ttu-id="fd5b5-109">在自定义类 `Person` 中，使用自定义 <xref:System.ComponentModel.TypeConverter> 的名称声明 <xref:System.ComponentModel.TypeConverter> 特性。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-109">In the custom class `Person`, a <xref:System.ComponentModel.TypeConverter> attribute is declared with the name of the custom <xref:System.ComponentModel.TypeConverter>.</span></span>  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   <span data-ttu-id="fd5b5-110">在自定义类 `Person` 中，重写 <xref:System.Object.Equals%2A> 和 <xref:System.Object.GetHashCode%2A> 类。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-110">In the custom class `Person`, the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> classes are overridden.</span></span>  
  
    ```  
    public override bool Equals(object obj)  
    {  
        Person person = obj as Person;  
  
        if (person != null)  
        {  
            return string.Equals(this.Name, person.Name);  
        }  
  
        return false;  
    }  
  
    public override int GetHashCode()  
    {  
        if (this.Name != null)  
        {  
            return this.Name.GetHashCode();  
        }  
  
        return 0;  
    }  
    ```  
  
-   <span data-ttu-id="fd5b5-111">实现自定义 <xref:System.ComponentModel.TypeConverter> 类，这将执行自定义类的实例与字符串之间的相互转换。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-111">A custom <xref:System.ComponentModel.TypeConverter> class is implemented that performs the conversion of an instance of the custom class to a string and a string to an instance of a custom class.</span></span>  
  
    ```  
    public class PersonConverter : TypeConverter  
    {  
        public override bool CanConvertFrom(ITypeDescriptorContext context,  
           Type sourceType)  
        {  
            return (sourceType is string);  
        }  
  
        // Overrides the ConvertFrom method of TypeConverter.  
        public override object ConvertFrom(ITypeDescriptorContext context,  
           CultureInfo culture, object value)  
        {  
            if (value == null)  
            {  
                return null;  
            }  
  
            if (value is string)  
            {  
                return new Person  
                {  
                    Name = (string)value  
                };  
            }  
  
            return base.ConvertFrom(context, culture, value);  
        }  
  
        // Overrides the ConvertTo method of TypeConverter.  
        public override object ConvertTo(ITypeDescriptorContext context,  
           CultureInfo culture, object value, Type destinationType)  
        {  
            if (destinationType == typeof(string))  
            {  
                if (value != null)  
                {  
                    return ((Person) value).Name;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
  
            return base.ConvertTo(context, culture, value, destinationType);  
        }  
    }  
    ```  
  
 <span data-ttu-id="fd5b5-112">此示例中包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="fd5b5-112">The following files are included in this sample:</span></span>  
  
-   <span data-ttu-id="fd5b5-113">**Person.cs**： 定义`Person`类。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-113">**Person.cs**: Defines the `Person` class.</span></span>  
  
-   <span data-ttu-id="fd5b5-114">**PersonConverter.cs**： 为的类型转换器`Person`类。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-114">**PersonConverter.cs**: The type converter for the `Person` class.</span></span>  
  
-   <span data-ttu-id="fd5b5-115">**Sequence.xaml**： 切换工作流`Person`类型。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-115">**Sequence.xaml**: a workflow that switches over the `Person` type.</span></span>  
  
-   <span data-ttu-id="fd5b5-116">**Program.cs**： 运行工作流的主函数。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-116">**Program.cs**: The main function that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="fd5b5-117">使用此示例</span><span class="sxs-lookup"><span data-stu-id="fd5b5-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="fd5b5-118">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载 Switch.sln。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-118">Load Switch.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="fd5b5-119">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-119">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="fd5b5-120">按 Ctrl+F5 运行示例。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-120">Press CTRL + F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fd5b5-121">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fd5b5-122">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="fd5b5-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fd5b5-123">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="fd5b5-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fd5b5-124">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="fd5b5-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a><span data-ttu-id="fd5b5-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd5b5-125">See Also</span></span>  
 [<span data-ttu-id="fd5b5-126">内置活动库</span><span class="sxs-lookup"><span data-stu-id="fd5b5-126">Built-In Activity Library</span></span>](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
