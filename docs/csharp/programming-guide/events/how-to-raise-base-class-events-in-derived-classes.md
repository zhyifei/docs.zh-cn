---
title: "如何：在派生类中引发基类事件（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 548409d3f632213f3ff1de0a27a70b9f42b18332
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="501a5-102">如何：在派生类中引发基类事件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="501a5-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="501a5-103">下面的简单示例演示用于在基类中声明事件，以便也可以从派生类引发它们的标准方法。</span><span class="sxs-lookup"><span data-stu-id="501a5-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="501a5-104">在 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 类库的 Windows 窗体类中广泛使用了此模式。</span><span class="sxs-lookup"><span data-stu-id="501a5-104">This pattern is used extensively in Windows Forms classes in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library.</span></span>  
  
 <span data-ttu-id="501a5-105">创建可以用作其他类的基类的类时，应考虑到以下事实：事件是特殊类型的委托，只能从声明它们的类中进行调用。</span><span class="sxs-lookup"><span data-stu-id="501a5-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="501a5-106">派生类不能直接调用在基类中声明的事件。</span><span class="sxs-lookup"><span data-stu-id="501a5-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="501a5-107">虽然有时可能需要只能由基类引发的事件，不过在大多数情况下，应使派生类可以调用基类事件。</span><span class="sxs-lookup"><span data-stu-id="501a5-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="501a5-108">为此，可以在包装事件的基类中创建受保护的调用方法。</span><span class="sxs-lookup"><span data-stu-id="501a5-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="501a5-109">通过调用或重写此调用方法，派生类可以间接调用事件。</span><span class="sxs-lookup"><span data-stu-id="501a5-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="501a5-110">不要在基类中声明虚拟事件并在派生类中重写它们。</span><span class="sxs-lookup"><span data-stu-id="501a5-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="501a5-111">C# 编译器不会处理这些事件，并且无法预知派生事件的订阅者是否实际上会订阅基类事件。</span><span class="sxs-lookup"><span data-stu-id="501a5-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="501a5-112">示例</span><span class="sxs-lookup"><span data-stu-id="501a5-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="501a5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="501a5-113">See Also</span></span>  
 [<span data-ttu-id="501a5-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="501a5-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="501a5-115">事件</span><span class="sxs-lookup"><span data-stu-id="501a5-115">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="501a5-116">委托</span><span class="sxs-lookup"><span data-stu-id="501a5-116">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="501a5-117">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="501a5-117">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="501a5-118">在 Windows 窗体中创建事件处理程序</span><span class="sxs-lookup"><span data-stu-id="501a5-118">Creating Event Handlers in Windows Forms</span></span>](https://msdn.microsoft.com/library/dacysss4.aspx)
