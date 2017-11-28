---
title: "如何：标识可以为 null 的类型（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 610ed18308df02c5632361cd09ef94330dea598b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="5e9fb-102">如何：标识可以为 null 的类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5e9fb-102">How to: Identify a Nullable Type (C# Programming Guide)</span></span>
<span data-ttu-id="5e9fb-103">可以使用 C# [typeof](../../../csharp/language-reference/keywords/typeof.md) 运算符创建表示可以为 null 的类型的 <xref:System.Type> 对象：</span><span class="sxs-lookup"><span data-stu-id="5e9fb-103">You can use the C# [typeof](../../../csharp/language-reference/keywords/typeof.md) operator to create a <xref:System.Type> object that represents a Nullable type:</span></span>  
  
```  
System.Type type = typeof(int?);  
```  
  
 <span data-ttu-id="5e9fb-104">还可以使用 <xref:System.Reflection> 命名空间的类和方法生成表示可以为 null 的类型的 <xref:System.Type> 对象。</span><span class="sxs-lookup"><span data-stu-id="5e9fb-104">You can also use the classes and methods of the <xref:System.Reflection> namespace to generate <xref:System.Type> objects that represent Nullable types.</span></span> <span data-ttu-id="5e9fb-105">但是，如果尝试使用 <xref:System.Object.GetType%2A> 方法或 `is` 运算符在运行时获取可以为 null 的变量的类型信息，则得到的结果是表示基础类型而不是可以为 null 的类型本身的 <xref:System.Type> 对象。</span><span class="sxs-lookup"><span data-stu-id="5e9fb-105">However, if you try to obtain type information from Nullable variables at runtime by using the <xref:System.Object.GetType%2A> method or the `is` operator, the result is a <xref:System.Type> object that represents the underlying type, not the Nullable type itself.</span></span>  
  
 <span data-ttu-id="5e9fb-106">对可以为 null 的类型调用 `GetType` 会导致在将该类型隐式转换为 <xref:System.Object> 时执行装箱操作。</span><span class="sxs-lookup"><span data-stu-id="5e9fb-106">Calling `GetType` on a Nullable type causes a boxing operation to be performed when the type is implicitly converted to <xref:System.Object>.</span></span> <span data-ttu-id="5e9fb-107">因此，<xref:System.Object.GetType%2A> 总是返回表示基础类型而不是可以为 null 的类型的 <xref:System.Type> 对象。</span><span class="sxs-lookup"><span data-stu-id="5e9fb-107">Therefore <xref:System.Object.GetType%2A> always returns a <xref:System.Type> object that represents the underlying type, not the Nullable type.</span></span>  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 <span data-ttu-id="5e9fb-108">C# 的 [is](../../../csharp/language-reference/keywords/is.md) 运算符还可以作用于可以为 null 的基础类型。</span><span class="sxs-lookup"><span data-stu-id="5e9fb-108">The C# [is](../../../csharp/language-reference/keywords/is.md) operator also operates on a Nullable's underlying type.</span></span> <span data-ttu-id="5e9fb-109">因此，不能使用 `is` 确定变量是否是可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="5e9fb-109">Therefore you cannot use `is` to determine whether a variable is a Nullable type.</span></span> <span data-ttu-id="5e9fb-110">以下示例演示 `is` 运算符将 Nullable\<int> 变量视为 int 变量。</span><span class="sxs-lookup"><span data-stu-id="5e9fb-110">The following example shows that the `is` operator treats a Nullable\<int> variable as an int.</span></span>  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a><span data-ttu-id="5e9fb-111">示例</span><span class="sxs-lookup"><span data-stu-id="5e9fb-111">Example</span></span>  
 <span data-ttu-id="5e9fb-112">使用下面的代码来确定 <xref:System.Type> 对象是否表示可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="5e9fb-112">Use the following code to determine whether a <xref:System.Type> object represents a Nullable type.</span></span> <span data-ttu-id="5e9fb-113">请记住，如果从对 <xref:System.Object.GetType%2A> 的调用返回`Type` 对象，则此代码始终返回 false，如本主题前面所述。</span><span class="sxs-lookup"><span data-stu-id="5e9fb-113">Remember that this code always returns false if the `Type` object was returned from a call to <xref:System.Object.GetType%2A>, as explained earlier in this topic.</span></span>  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e9fb-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e9fb-114">See Also</span></span>  
 [<span data-ttu-id="5e9fb-115">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="5e9fb-115">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="5e9fb-116">装箱可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="5e9fb-116">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)
