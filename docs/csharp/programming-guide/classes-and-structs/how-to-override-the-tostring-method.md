---
title: "如何：重写 ToString 方法（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5b0f7bf35e5bd565e0bfa46fe91cf86aedcd2d8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="2ab88-102">如何：重写 ToString 方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2ab88-102">How to: Override the ToString Method (C# Programming Guide)</span></span>
<span data-ttu-id="2ab88-103">C# 中的每个类或结构都可隐式继承 <xref:System.Object> 类。</span><span class="sxs-lookup"><span data-stu-id="2ab88-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="2ab88-104">因此，C# 中的每个对象都会获取 <xref:System.Object.ToString%2A> 方法，该方法返回该对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="2ab88-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="2ab88-105">例如，类型为 `int` 的所有变量都有一个 `ToString` 方法，使它们可以将其内容作为字符串返回：</span><span class="sxs-lookup"><span data-stu-id="2ab88-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 <span data-ttu-id="2ab88-106">创建自定义类或结构时，应替代 <xref:System.Object.ToString%2A> 方法，以向客户端代码提供有关你的类型的信息。</span><span class="sxs-lookup"><span data-stu-id="2ab88-106">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="2ab88-107">若要深入了解如何通过 `ToString` 方法使用格式字符串和其他类型的自定义格式设置，请参阅[格式化类型](../../../standard/base-types/formatting-types.md)。</span><span class="sxs-lookup"><span data-stu-id="2ab88-107">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ab88-108">决定通过此方法提供信息内容时，请考虑你的类或结构是否会被不受信任的代码使用。</span><span class="sxs-lookup"><span data-stu-id="2ab88-108">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="2ab88-109">请务必确保不提供可能被恶意代码利用的任何信息。</span><span class="sxs-lookup"><span data-stu-id="2ab88-109">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a><span data-ttu-id="2ab88-110">替代类或结构中的 ToString 方法</span><span class="sxs-lookup"><span data-stu-id="2ab88-110">To override the ToString method in your class or struct</span></span>  
  
1.  <span data-ttu-id="2ab88-111">声明具有下列修饰符和返回类型的 `ToString` 方法：</span><span class="sxs-lookup"><span data-stu-id="2ab88-111">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  <span data-ttu-id="2ab88-112">实现该方法，使其返回一个字符串。</span><span class="sxs-lookup"><span data-stu-id="2ab88-112">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="2ab88-113">下面的示例返回类的名称，但特定于该类的特定实例的数据除外。</span><span class="sxs-lookup"><span data-stu-id="2ab88-113">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     <span data-ttu-id="2ab88-114">可以测试 `ToString` 方法，如以下代码示例所示：</span><span class="sxs-lookup"><span data-stu-id="2ab88-114">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2ab88-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ab88-115">See Also</span></span>  
 <xref:System.IFormattable>  
 [<span data-ttu-id="2ab88-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2ab88-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2ab88-117">类和结构</span><span class="sxs-lookup"><span data-stu-id="2ab88-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="2ab88-118">字符串</span><span class="sxs-lookup"><span data-stu-id="2ab88-118">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="2ab88-119">字符串</span><span class="sxs-lookup"><span data-stu-id="2ab88-119">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
 [<span data-ttu-id="2ab88-120">new</span><span class="sxs-lookup"><span data-stu-id="2ab88-120">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="2ab88-121">替代</span><span class="sxs-lookup"><span data-stu-id="2ab88-121">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="2ab88-122">virtual</span><span class="sxs-lookup"><span data-stu-id="2ab88-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
 [<span data-ttu-id="2ab88-123">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="2ab88-123">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
