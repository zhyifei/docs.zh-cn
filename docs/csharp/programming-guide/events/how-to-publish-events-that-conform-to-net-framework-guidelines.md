---
title: 如何：发布符合 .NET Framework 准则的事件（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 9a17aaec20b03325abadfcc168f7ac4653f300df
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "47401506"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a><span data-ttu-id="a095d-102">如何：发布符合 .NET Framework 准则的事件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a095d-102">How to: Publish Events that Conform to .NET Framework Guidelines (C# Programming Guide)</span></span>
<span data-ttu-id="a095d-103">下面的过程演示了如何将遵循标准 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 模式的事件添加到类和结构中。</span><span class="sxs-lookup"><span data-stu-id="a095d-103">The following procedure demonstrates how to add events that follow the standard [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pattern to your classes and structs.</span></span> <span data-ttu-id="a095d-104">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 类库中的所有事件均基于 <xref:System.EventHandler> 委托，定义如下：</span><span class="sxs-lookup"><span data-stu-id="a095d-104">All events in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  <span data-ttu-id="a095d-105">[!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] 引入了泛型版本的委托 <xref:System.EventHandler%601>。</span><span class="sxs-lookup"><span data-stu-id="a095d-105">The [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="a095d-106">下例演示了如何使用这两个版本。</span><span class="sxs-lookup"><span data-stu-id="a095d-106">The following examples show how to use both versions.</span></span>  
  
 <span data-ttu-id="a095d-107">尽管定义的类中的事件可基于任何有效委托类型，甚至是返回值的委托，但一般还是建议使用 <xref:System.EventHandler> 使事件基于 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 模式，如下例中所示。</span><span class="sxs-lookup"><span data-stu-id="a095d-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="a095d-108">发布基于 EventHandler 模式的事件</span><span class="sxs-lookup"><span data-stu-id="a095d-108">To publish events based on the EventHandler pattern</span></span>  
  
1.  <span data-ttu-id="a095d-109">（如果无需随事件一起发送自定义数据，请跳过此步骤转到步骤 3a。）将自定义数据的类声明为对发布服务器和订阅者类均可见的范围。</span><span class="sxs-lookup"><span data-stu-id="a095d-109">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="a095d-110">然后添加所需成员以保留自定义事件数据。</span><span class="sxs-lookup"><span data-stu-id="a095d-110">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="a095d-111">在此示例中，将返回一个简单的字符串。</span><span class="sxs-lookup"><span data-stu-id="a095d-111">In this example, a simple string is returned.</span></span>  
  
    ```csharp  
    public class CustomEventArgs : EventArgs  
    {  
        public CustomEventArgs(string s)  
        {  
            msg = s;  
        }  
        private string msg;  
        public string Message  
        {  
            get { return msg; }  
        }   
    }  
    ```  
  
2.  <span data-ttu-id="a095d-112">（如果正在使用泛型版本 <xref:System.EventHandler%601>，请跳过此步骤。）声明发布类中的委托。</span><span class="sxs-lookup"><span data-stu-id="a095d-112">(Skip this step if you are using the generic version of <xref:System.EventHandler%601> .) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="a095d-113">为以 EventHandler 结尾的委托命名。</span><span class="sxs-lookup"><span data-stu-id="a095d-113">Give it a name that ends with *EventHandler*.</span></span> <span data-ttu-id="a095d-114">第二个参数指定自定义 EventArgs 类型。</span><span class="sxs-lookup"><span data-stu-id="a095d-114">The second parameter specifies your custom EventArgs type.</span></span>  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3.  <span data-ttu-id="a095d-115">使用下列步骤之一来声明发布类中的事件。</span><span class="sxs-lookup"><span data-stu-id="a095d-115">Declare the event in your publishing class by using one of the following steps.</span></span>  
  
    1.  <span data-ttu-id="a095d-116">如果没有任何自定义 EventArgs 类，事件类型将为非泛型 EventHandler 委托。</span><span class="sxs-lookup"><span data-stu-id="a095d-116">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="a095d-117">你无需声明该委托，因为它已在创建 C# 项目时包括的 <xref:System> 命名空间中声明。</span><span class="sxs-lookup"><span data-stu-id="a095d-117">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="a095d-118">将以下代码添加到发布服务器类。</span><span class="sxs-lookup"><span data-stu-id="a095d-118">Add the following code to your publisher class.</span></span>  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2.  <span data-ttu-id="a095d-119">如果使用非泛型版本 <xref:System.EventHandler> 并且具有派生自 <xref:System.EventArgs> 的自定义类，请声明发布类中的事件，并将步骤 2 中的委托用作类型。</span><span class="sxs-lookup"><span data-stu-id="a095d-119">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3.  <span data-ttu-id="a095d-120">如果使用泛型版本，则无需自定义委托。</span><span class="sxs-lookup"><span data-stu-id="a095d-120">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="a095d-121">而是在发布类中，将事件类型指定为 `EventHandler<CustomEventArgs>`，替换尖括号中自定义类的名称。</span><span class="sxs-lookup"><span data-stu-id="a095d-121">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a><span data-ttu-id="a095d-122">示例</span><span class="sxs-lookup"><span data-stu-id="a095d-122">Example</span></span>  
 <span data-ttu-id="a095d-123">下例通过使用自定义 EventArgs 类和 <xref:System.EventHandler%601> 作为事件类型来演示之前的步骤。</span><span class="sxs-lookup"><span data-stu-id="a095d-123">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>  
  
 [!code-csharp[csProgGuideEvents#2](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-publish-events-that-conform-to-net-framework-guidelines_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a095d-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="a095d-124">See Also</span></span>

- <xref:System.Delegate>  
- [<span data-ttu-id="a095d-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a095d-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a095d-126">事件</span><span class="sxs-lookup"><span data-stu-id="a095d-126">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="a095d-127">委托</span><span class="sxs-lookup"><span data-stu-id="a095d-127">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
