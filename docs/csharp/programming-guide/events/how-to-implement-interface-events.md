---
title: 如何实现接口事件 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 8c0d221ef1272a43e2682ef2af3fa37d2d12d35e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167475"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="3426f-102">如何实现接口事件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3426f-102">How to implement interface events (C# Programming Guide)</span></span>
<span data-ttu-id="3426f-103">[接口](../../language-reference/keywords/interface.md)可以声明[事件](../../language-reference/keywords/event.md)。</span><span class="sxs-lookup"><span data-stu-id="3426f-103">An [interface](../../language-reference/keywords/interface.md) can declare an [event](../../language-reference/keywords/event.md).</span></span> <span data-ttu-id="3426f-104">下面的示例演示如何在类中实现接口事件。</span><span class="sxs-lookup"><span data-stu-id="3426f-104">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="3426f-105">这些规则基本上都与实现任何接口方法或属性时的相同。</span><span class="sxs-lookup"><span data-stu-id="3426f-105">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="3426f-106">在类中实现接口事件</span><span class="sxs-lookup"><span data-stu-id="3426f-106">To implement interface events in a class</span></span>  
  
<span data-ttu-id="3426f-107">在类中声明事件，然后在相应区域中调用它。</span><span class="sxs-lookup"><span data-stu-id="3426f-107">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
```csharp
namespace ImplementInterfaceEvents  
{  
    public interface IDrawingObject  
    {  
        event EventHandler ShapeChanged;  
    }  
    public class MyEventArgs : EventArgs
    {  
        // class members  
    }  
    public class Shape : IDrawingObject  
    {  
        public event EventHandler ShapeChanged;  
        void ChangeShape()  
        {  
            // Do something here before the event…  

            OnShapeChanged(new MyEventArgs(/*arguments*/));  

            // or do something here after the event.
        }  
        protected virtual void OnShapeChanged(MyEventArgs e)  
        {  
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a><span data-ttu-id="3426f-108">示例</span><span class="sxs-lookup"><span data-stu-id="3426f-108">Example</span></span>  
<span data-ttu-id="3426f-109">下面的示例演示如何处理不太常见的情况：类继承自两个或多个接口，且每个接口都具有相同名称的事件。</span><span class="sxs-lookup"><span data-stu-id="3426f-109">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="3426f-110">在这种情况下，你必须为至少其中一个事件提供显式接口实现。</span><span class="sxs-lookup"><span data-stu-id="3426f-110">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="3426f-111">为事件编写显式接口实现时，还必须编写 `add` 和 `remove` 事件访问器。</span><span class="sxs-lookup"><span data-stu-id="3426f-111">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="3426f-112">通常这些访问器由编译器提供，但在这种情况下编译器不提供它们。</span><span class="sxs-lookup"><span data-stu-id="3426f-112">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="3426f-113">通过提供自己的访问器，可以指定两个事件是由类中的同一个事件表示，还是由不同事件表示。</span><span class="sxs-lookup"><span data-stu-id="3426f-113">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="3426f-114">例如，如果根据接口规范应在不同时间引发事件，可以在类中将每个事件与单独实现关联。</span><span class="sxs-lookup"><span data-stu-id="3426f-114">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="3426f-115">在下面的示例中，订阅服务器确定它们通过将形状引用转换为 `OnDraw` 或 `IShape` 接收哪个 `IDrawingObject` 事件。</span><span class="sxs-lookup"><span data-stu-id="3426f-115">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a><span data-ttu-id="3426f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3426f-116">See also</span></span>

- [<span data-ttu-id="3426f-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3426f-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3426f-118">事件</span><span class="sxs-lookup"><span data-stu-id="3426f-118">Events</span></span>](./index.md)
- [<span data-ttu-id="3426f-119">委托</span><span class="sxs-lookup"><span data-stu-id="3426f-119">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="3426f-120">显式接口实现</span><span class="sxs-lookup"><span data-stu-id="3426f-120">Explicit Interface Implementation</span></span>](../interfaces/explicit-interface-implementation.md)
- [<span data-ttu-id="3426f-121">如何在派生类中引发基类事件</span><span class="sxs-lookup"><span data-stu-id="3426f-121">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)
