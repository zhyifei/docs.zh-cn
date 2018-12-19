---
title: 自动实现的属性 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 1277e0908b42b6f8185219a33c2b28537c8b6607
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244188"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="1f80a-102">自动实现的属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1f80a-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="1f80a-103">在 C# 3.0 及更高版本，当属性访问器中不需要任何其他逻辑时，自动实现的属性会使属性声明更加简洁。</span><span class="sxs-lookup"><span data-stu-id="1f80a-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="1f80a-104">它们还允许客户端代码创建对象。</span><span class="sxs-lookup"><span data-stu-id="1f80a-104">They also enable client code to create objects.</span></span> <span data-ttu-id="1f80a-105">当你声明以下示例中所示的属性时，编译器将创建仅可以通过该属性的 `get` 和 `set` 访问器访问的专用、匿名支持字段。</span><span class="sxs-lookup"><span data-stu-id="1f80a-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f80a-106">示例</span><span class="sxs-lookup"><span data-stu-id="1f80a-106">Example</span></span>  
 <span data-ttu-id="1f80a-107">下列示例演示一个简单的类，它具有某些自动实现的属性：</span><span class="sxs-lookup"><span data-stu-id="1f80a-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 <span data-ttu-id="1f80a-108">在 C# 6 和更高版本中，你可以像字段一样初始化自动实现属性：</span><span class="sxs-lookup"><span data-stu-id="1f80a-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="1f80a-109">上一示例中所示的类是可变的。</span><span class="sxs-lookup"><span data-stu-id="1f80a-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="1f80a-110">创建客户端代码后可以用于更改对象中的值。</span><span class="sxs-lookup"><span data-stu-id="1f80a-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="1f80a-111">在包含重要行为（方法）以及数据的复杂类中，通常有必要具有公共属性。</span><span class="sxs-lookup"><span data-stu-id="1f80a-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="1f80a-112">但是，对于较小类或仅封装一组值（数据）且只有很少行为或没有行为的结构，则应该通过声明 set 访问器为[专用](../../../csharp/language-reference/keywords/private.md)（对使用者的不可变）或通过声明仅一个 get 访问器（除构造函数外都不可变），使对象不可变。</span><span class="sxs-lookup"><span data-stu-id="1f80a-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../../csharp/language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="1f80a-113">有关更多信息，请参见[如何：使用自动实现的属性实现轻量类](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1f80a-113">For more information, see [How to: Implement a Lightweight Class with Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="1f80a-114">自动实现的属性上允许使用特性，但很明显支持字段上不允许，因为不能从你的源代码访问它们。</span><span class="sxs-lookup"><span data-stu-id="1f80a-114">Attributes are permitted on auto-implemented properties but obviously not on the backing fields since those are not accessible from your source code.</span></span> <span data-ttu-id="1f80a-115">如果必须使用属性的支持字段上的特性，只需创建一个常规属性。</span><span class="sxs-lookup"><span data-stu-id="1f80a-115">If you must use an attribute on the backing field of a property, just create a regular property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f80a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f80a-116">See Also</span></span>

- [<span data-ttu-id="1f80a-117">属性</span><span class="sxs-lookup"><span data-stu-id="1f80a-117">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [<span data-ttu-id="1f80a-118">修饰符</span><span class="sxs-lookup"><span data-stu-id="1f80a-118">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
