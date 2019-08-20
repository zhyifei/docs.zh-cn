---
title: ':: 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 08/09/2019
f1_keywords:
- ::_CSharpKeyword
- global_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- namespace alias qualifier [C#]
- namespace [C#]
- global keyword [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2aceb51747708b12fb3059b097b72206c78a9d5d
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971242"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6f343-102">:: 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6f343-102">:: operator (C# reference)</span></span>

<span data-ttu-id="6f343-103">使用命名空间别名限定符 `::` 访问已设置别名的命名空间的成员。</span><span class="sxs-lookup"><span data-stu-id="6f343-103">Use the namespace alias qualifier `::` to access members of an aliased namespace.</span></span> <span data-ttu-id="6f343-104">使用两个标识符之间的 `::` 限定符。</span><span class="sxs-lookup"><span data-stu-id="6f343-104">You use the `::` qualifier between two identifiers.</span></span> <span data-ttu-id="6f343-105">左侧标识符可以是以下任意别名：</span><span class="sxs-lookup"><span data-stu-id="6f343-105">The left-hand identifier can be any of the following aliases:</span></span>

- <span data-ttu-id="6f343-106">使用 [using 别名指令](../keywords/using-directive.md)创建的命名空间别名：</span><span class="sxs-lookup"><span data-stu-id="6f343-106">A namespace alias created with the [using alias directive](../keywords/using-directive.md):</span></span>
  
  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- <span data-ttu-id="6f343-107">[外部别名](../keywords/extern-alias.md)。</span><span class="sxs-lookup"><span data-stu-id="6f343-107">An [extern alias](../keywords/extern-alias.md).</span></span>
- <span data-ttu-id="6f343-108">`global` 别名，该别名是全局命名空间别名。</span><span class="sxs-lookup"><span data-stu-id="6f343-108">The `global` alias, which is the global namespace alias.</span></span> <span data-ttu-id="6f343-109">全局命名空间是包含未在命名空间中声明的命名空间和类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6f343-109">The global namespace is the namespace that contains namespaces and types that are not declared inside a named namespace.</span></span> <span data-ttu-id="6f343-110">与 `::` 限定符一起使用时，`global` 别名始终引用全局命名空间，即使存在用户定义的 `global` 命名空间别名也是如此。</span><span class="sxs-lookup"><span data-stu-id="6f343-110">When used with the `::` qualifier, the `global` alias always references the global namespace, even if there is the user-defined `global` namespace alias.</span></span>
  
  <span data-ttu-id="6f343-111">以下示例使用 `global` 别名访问 .NET <xref:System> 命名空间，该命名空间是全局命名空间的成员。</span><span class="sxs-lookup"><span data-stu-id="6f343-111">The following example uses the `global` alias to access the .NET <xref:System> namespace, which is a member of the global namespace.</span></span> <span data-ttu-id="6f343-112">如果没有 `global` 别名，则将访问用户定义的 `System` 命名空间（该命名空间是 `MyCompany.MyProduct` 命名空间的成员）：</span><span class="sxs-lookup"><span data-stu-id="6f343-112">Without the `global` alias, the user-defined `System` namespace, which is a member of the `MyCompany.MyProduct` namespace, would be accessed:</span></span>

  ```csharp
  namespace MyCompany.MyProduct.System
  {
      class Program
      {
          static void Main() => global::System.Console.WriteLine("Using global alias");
      }
  
      class Console
      {
          string Suggestion => "Consider renaming this class";
      }
  }
  ```
  
  > [!NOTE]
  > <span data-ttu-id="6f343-113">仅当 `global` 关键字是 `::` 限定符的左侧标识符时，该关键字才是全局命名空间别名。</span><span class="sxs-lookup"><span data-stu-id="6f343-113">The `global` keyword is the global namespace alias only when it's the left-hand identifier of the `::` qualifier.</span></span>

<span data-ttu-id="6f343-114">你还可以使用[成员访问 `.` 运算符](member-access-operators.md#member-access-operator-)来访问别名命名空间的成员。</span><span class="sxs-lookup"><span data-stu-id="6f343-114">You can also use the [member access `.` operator](member-access-operators.md#member-access-operator-) to access members of an aliased namespace.</span></span> <span data-ttu-id="6f343-115">但是，`.` 运算符还用于访问类型的成员。</span><span class="sxs-lookup"><span data-stu-id="6f343-115">However, the `.` operator is also used to access members of a type.</span></span> <span data-ttu-id="6f343-116">`::` 限定符确保其左侧标识符始终引用命名空间别名，即使存在同名的类型或命名空间也是如此。</span><span class="sxs-lookup"><span data-stu-id="6f343-116">The `::` qualifier ensures that its left-hand identifier always references a namespace alias, even if there exists a type or namespace with the same name.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6f343-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="6f343-117">C# language specification</span></span>

<span data-ttu-id="6f343-118">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[命名空间别名限定符](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers)部分。</span><span class="sxs-lookup"><span data-stu-id="6f343-118">For more information, see the [Namespace alias qualifiers](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f343-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f343-119">See also</span></span>

- [<span data-ttu-id="6f343-120">C# 参考</span><span class="sxs-lookup"><span data-stu-id="6f343-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6f343-121">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="6f343-121">C# operators</span></span>](index.md)
- [<span data-ttu-id="6f343-122">using 命名空间</span><span class="sxs-lookup"><span data-stu-id="6f343-122">Using namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
