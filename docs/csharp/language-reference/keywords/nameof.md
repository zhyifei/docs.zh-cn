---
title: nameof - C# 参考
ms.custom: seodec18
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5641b31a7fe380b2d19969f4baa7a701d74de4c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638708"
---
# <a name="nameof-c-reference"></a><span data-ttu-id="503cd-102">nameof（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="503cd-102">nameof (C# Reference)</span></span>

<span data-ttu-id="503cd-103">用于获取变量、类型或成员的简单（非限定）字符串名称。</span><span class="sxs-lookup"><span data-stu-id="503cd-103">Used to obtain the simple (unqualified) string name of a variable, type, or member.</span></span>  

<span data-ttu-id="503cd-104">在报告代码中的错误、挂接“模型-视图-控制器”(MVC) 链接、触发属性更改事件时，你通常会希望捕获方法的字符串名称。</span><span class="sxs-lookup"><span data-stu-id="503cd-104">When reporting errors in code, hooking up model-view-controller (MVC) links, firing property changed events, etc., you often want to capture the string name of a method.</span></span>  <span data-ttu-id="503cd-105">使用 `nameof` 有助于在重命名定义时使代码始终有效。</span><span class="sxs-lookup"><span data-stu-id="503cd-105">Using `nameof` helps keep your code valid when renaming definitions.</span></span>  <span data-ttu-id="503cd-106">以前必须使用字符串来引用定义，在重命名代码元素时，此方法很脆弱，因为工具不知道要检查这些字符串。</span><span class="sxs-lookup"><span data-stu-id="503cd-106">Before, you had to use string literals to refer to definitions, which is brittle when renaming code elements because tools do not know to check these string literals.</span></span>  
  
 <span data-ttu-id="503cd-107">`nameof` 表达式具有此形式：</span><span class="sxs-lookup"><span data-stu-id="503cd-107">A `nameof` expression has this form:</span></span>  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a><span data-ttu-id="503cd-108">关键用例</span><span class="sxs-lookup"><span data-stu-id="503cd-108">Key Use Cases</span></span>  
 <span data-ttu-id="503cd-109">这些示例显示 `nameof` 的关键用例。</span><span class="sxs-lookup"><span data-stu-id="503cd-109">These examples show the key use cases for `nameof`.</span></span>  
  
 <span data-ttu-id="503cd-110">验证参数：</span><span class="sxs-lookup"><span data-stu-id="503cd-110">Validate parameters:</span></span>  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 <span data-ttu-id="503cd-111">MVC 操作链接：</span><span class="sxs-lookup"><span data-stu-id="503cd-111">MVC Action links:</span></span>  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 <span data-ttu-id="503cd-112">INotifyPropertyChanged：</span><span class="sxs-lookup"><span data-stu-id="503cd-112">INotifyPropertyChanged:</span></span>  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 <span data-ttu-id="503cd-113">XAML 依赖项属性：</span><span class="sxs-lookup"><span data-stu-id="503cd-113">XAML dependency property:</span></span>  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 <span data-ttu-id="503cd-114">日志记录：</span><span class="sxs-lookup"><span data-stu-id="503cd-114">Logging:</span></span>  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 <span data-ttu-id="503cd-115">特性:</span><span class="sxs-lookup"><span data-stu-id="503cd-115">Attributes:</span></span>  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a><span data-ttu-id="503cd-116">示例</span><span class="sxs-lookup"><span data-stu-id="503cd-116">Examples</span></span>  
 <span data-ttu-id="503cd-117">一些 C# 示例：</span><span class="sxs-lookup"><span data-stu-id="503cd-117">Some C# examples:</span></span>  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
class Test {  
    static void Main (string[] args) {  
        Console.WriteLine(nameof(C)); // -> "C"  
        Console.WriteLine(nameof(C.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(C.Method2)); // -> "Method2"  
        Console.WriteLine(nameof(c.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(c.Method2)); // -> "Method2"  
        // Console.WriteLine(nameof(z)); -> "z" [inside of Method2 ok, inside Method1 is a compiler error]  
        Console.WriteLine(nameof(Stuff)); // -> "Stuff"  
        // Console.WriteLine(nameof(T)); -> "T" [works inside of method but not in attributes on the method]  
        Console.WriteLine(nameof(f)); // -> "f"  
        // Console.WriteLine(nameof(f<T>)); -> [syntax error]  
        // Console.WriteLine(nameof(f<>)); -> [syntax error]  
        // Console.WriteLine(nameof(Method2())); -> [error "This expression does not have a name"]  
    }
}
```  
  
## <a name="remarks"></a><span data-ttu-id="503cd-118">备注</span><span class="sxs-lookup"><span data-stu-id="503cd-118">Remarks</span></span>  
 <span data-ttu-id="503cd-119">`nameof` 的参数必须是简单名称、限定名称、成员访问、指定成员的基访问或指定成员的此类访问。</span><span class="sxs-lookup"><span data-stu-id="503cd-119">The argument to `nameof` must be a simple name, qualified name, member access, base access with a specified member, or this access with a specified member.</span></span>  <span data-ttu-id="503cd-120">参数表达式标识代码定义，但从不进行计算。</span><span class="sxs-lookup"><span data-stu-id="503cd-120">The argument expression identifies a code definition, but it is never evaluated.</span></span>  
  
 <span data-ttu-id="503cd-121">因为在语法上参数必须为表达式，因此有很多禁用内容无需列出。</span><span class="sxs-lookup"><span data-stu-id="503cd-121">Because the argument needs to be an expression syntactically, there are many things disallowed that are not useful to list.</span></span>  <span data-ttu-id="503cd-122">以下内容会产生错误，值得一提：预定义的类型（如 `int` 或 `void`）、可以为 null 的类型（`Point?`）、数组类型（`Customer[,]`）、指针类型 (`Buffer*`)、限定别名 (`A::B`)、未绑定的泛型类型 (`Dictionary<,>`)、预处理符号 (`DEBUG`) 和标签 (`loop:`)。</span><span class="sxs-lookup"><span data-stu-id="503cd-122">The following are worth mentioning that produce errors: predefined types (for example, `int` or `void`), nullable types (`Point?`), array types (`Customer[,]`), pointer types (`Buffer*`), qualified alias (`A::B`), and unbound generic types (`Dictionary<,>`), preprocessing symbols (`DEBUG`), and labels (`loop:`).</span></span>  
  
 <span data-ttu-id="503cd-123">如果需要获取完全限定名，可以将 `typeof` 表达式和 `nameof`结合使用。</span><span class="sxs-lookup"><span data-stu-id="503cd-123">If you need to get the fully-qualified name, you can use the `typeof` expression along with `nameof`.</span></span>  <span data-ttu-id="503cd-124">例如:</span><span class="sxs-lookup"><span data-stu-id="503cd-124">For example:</span></span>
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 <span data-ttu-id="503cd-125">遗憾的是，`typeof` 不是类似于 `nameof` 的常数表达式，因此，不能在 `nameof` 的所有相同位置将 `typeof` 和 `nameof` 结合使用。</span><span class="sxs-lookup"><span data-stu-id="503cd-125">Unfortunately `typeof` is not a constant expression like `nameof`, so `typeof` cannot be used in conjunction with `nameof` in all the same places as `nameof`.</span></span>  <span data-ttu-id="503cd-126">例如，以下操作会导致 CS0182 编译错误：</span><span class="sxs-lookup"><span data-stu-id="503cd-126">For example, the following would cause a CS0182 compile error:</span></span>
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 <span data-ttu-id="503cd-127">在这些示例中，显示了可使用类型名称并访问实例方法名称。</span><span class="sxs-lookup"><span data-stu-id="503cd-127">In the examples you see that you can use a type name and access an instance method name.</span></span>  <span data-ttu-id="503cd-128">按照计算表达式的要求，无需具有类型的实例。</span><span class="sxs-lookup"><span data-stu-id="503cd-128">You do not need to have an instance of the type, as required in evaluated expressions.</span></span>  <span data-ttu-id="503cd-129">在某些情况下使用类型名称非常方便，因为只引用名称而不使用实例数据，因此不必构建实例变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="503cd-129">Using the type name can be very convenient in some situations, and since you are just referring to the name and not using instance data, you do not need to contrive an instance variable or expression.</span></span>  
  
 <span data-ttu-id="503cd-130">你可以引用类中特性表达式的类成员。</span><span class="sxs-lookup"><span data-stu-id="503cd-130">You can reference the members of a class in attribute expressions on the class.</span></span>  
  
 <span data-ttu-id="503cd-131">无法获取类似于“`Method1 (str, str)`”的签名信息。</span><span class="sxs-lookup"><span data-stu-id="503cd-131">There is no way to get a signatures information such as "`Method1 (str, str)`".</span></span>  <span data-ttu-id="503cd-132">实现该操作的一种方法是使用表达式 `Expression e = () => A.B.Method1("s1", "s2")`，并从生成的表达式树中拉取 MemberInfo。</span><span class="sxs-lookup"><span data-stu-id="503cd-132">One way to do that is to use an Expression, `Expression e = () => A.B.Method1("s1", "s2")`, and pull the MemberInfo from the resulting expression tree.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="503cd-133">语言规范</span><span class="sxs-lookup"><span data-stu-id="503cd-133">Language Specifications</span></span>  

<span data-ttu-id="503cd-134">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [Nameof 表达式](~/_csharplang/spec/expressions.md#nameof-expressions)。</span><span class="sxs-lookup"><span data-stu-id="503cd-134">For more information, see [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="503cd-135">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="503cd-135">The language specification is the definitive source for C# syntax and usage.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="503cd-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="503cd-136">See also</span></span>

- [<span data-ttu-id="503cd-137">C# 参考</span><span class="sxs-lookup"><span data-stu-id="503cd-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="503cd-138">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="503cd-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="503cd-139">typeof</span><span class="sxs-lookup"><span data-stu-id="503cd-139">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
