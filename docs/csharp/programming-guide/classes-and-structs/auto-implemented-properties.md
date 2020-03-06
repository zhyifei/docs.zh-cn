---
title: 自动实现的属性 - C# 编程指南
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 989266bfc2de9bd5ce2948f09a2b9f19dd2c782e
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628288"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="e8d6b-102">自动实现的属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e8d6b-102">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="e8d6b-103">在 C# 3.0 及更高版本，当属性访问器中不需要任何其他逻辑时，自动实现的属性会使属性声明更加简洁。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="e8d6b-104">它们还允许客户端代码创建对象。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-104">They also enable client code to create objects.</span></span> <span data-ttu-id="e8d6b-105">当你声明以下示例中所示的属性时，编译器将创建仅可以通过该属性的 `get` 和 `set` 访问器访问的专用、匿名支持字段。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>
  
## <a name="example"></a><span data-ttu-id="e8d6b-106">示例</span><span class="sxs-lookup"><span data-stu-id="e8d6b-106">Example</span></span>

<span data-ttu-id="e8d6b-107">下列示例演示一个简单的类，它具有某些自动实现的属性：</span><span class="sxs-lookup"><span data-stu-id="e8d6b-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="e8d6b-108">不能在接口中声明自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-108">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="e8d6b-109">自动实现的属性声明一个私有实例支持字段，并且接口可能不声明实例字段。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-109">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="e8d6b-110">如果在接口中声明属性而不定义主体，请使用访问器声明属性，访问器必须由实现该接口的每个类型实现。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-110">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="e8d6b-111">在 C# 6 和更高版本中，你可以像字段一样初始化自动实现属性：</span><span class="sxs-lookup"><span data-stu-id="e8d6b-111">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
 
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
 
<span data-ttu-id="e8d6b-112">上一示例中所示的类是可变的。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-112">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="e8d6b-113">客户端代码在创建后可以更改对象中的值。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-113">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="e8d6b-114">在包含重要行为（方法）以及数据的复杂类中，通常有必要具有公共属性。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-114">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="e8d6b-115">但是，对于较小类或仅封装一组值（数据）且只有很少行为或没有行为的结构，则应该通过声明 set 访问器为[专用](../../language-reference/keywords/private.md)（对使用者的不可变）或通过声明仅一个 get 访问器（除构造函数外都不可变），使对象不可变。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-115">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="e8d6b-116">有关详细信息，请参阅[如何使用自动实现的属性实现轻量类](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="e8d6b-116">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8d6b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8d6b-117">See also</span></span>

- [<span data-ttu-id="e8d6b-118">属性</span><span class="sxs-lookup"><span data-stu-id="e8d6b-118">Properties</span></span>](./properties.md)
- [<span data-ttu-id="e8d6b-119">修饰符</span><span class="sxs-lookup"><span data-stu-id="e8d6b-119">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
