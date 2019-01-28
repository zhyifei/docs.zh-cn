---
title: 标识符名称
description: 了解 C# 编程语言中有效标识符名称的规则。
ms.date: 08/21/2018
ms.openlocfilehash: 2147b3846d4ba6d5471b81448489c6d716e3cd61
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606947"
---
# <a name="identifier-names"></a><span data-ttu-id="62eb7-103">标识符名称</span><span class="sxs-lookup"><span data-stu-id="62eb7-103">Identifier names</span></span>

<span data-ttu-id="62eb7-104">标识符是分配给类型（类、接口、结构、委托或枚举）、成员、变量或命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="62eb7-104">An **identifier** is the name you assign to a type (class, interface, struct, delegate, or enum), member, variable, or namespace.</span></span> <span data-ttu-id="62eb7-105">有效标识符必须遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="62eb7-105">Valid identifiers must follow these rules:</span></span>

- <span data-ttu-id="62eb7-106">标识符必须以字母或 `_` 开头。</span><span class="sxs-lookup"><span data-stu-id="62eb7-106">Identifiers must start with a letter, or `_`.</span></span>
- <span data-ttu-id="62eb7-107">标识符可以包含 Unicode 字母字符、十进制数字字符、Unicode 连接字符、Unicode 组合字符或 Unicode 格式字符。</span><span class="sxs-lookup"><span data-stu-id="62eb7-107">Identifiers may contain Unicode letter characters, decimal digit characters, Unicode connecting characters, Unicode combining characters, or Unicode formatting characters.</span></span> <span data-ttu-id="62eb7-108">有关 Unicode 类别的详细信息，请参阅 [Unicode 类别数据库](https://www.unicode.org/reports/tr44/)。</span><span class="sxs-lookup"><span data-stu-id="62eb7-108">For more information on Unicode categories, see the [Unicode Category Database](https://www.unicode.org/reports/tr44/).</span></span>
<span data-ttu-id="62eb7-109">可以在标识符上使用 `@` 前缀来声明与 C# 关键字匹配的标识符。</span><span class="sxs-lookup"><span data-stu-id="62eb7-109">You can declare identifiers that match C# keywords by using the `@` prefix on the identifier.</span></span> <span data-ttu-id="62eb7-110">`@` 不是标识符名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="62eb7-110">The `@` is not part of the identifier name.</span></span> <span data-ttu-id="62eb7-111">例如，`@if` 声明名为 `if` 的标识符。</span><span class="sxs-lookup"><span data-stu-id="62eb7-111">For example, `@if` declares an identifier named `if`.</span></span> <span data-ttu-id="62eb7-112">这些[逐字标识符](../../language-reference/tokens/verbatim.md)主要用于与使用其他语言声明的标识符的互操作性。</span><span class="sxs-lookup"><span data-stu-id="62eb7-112">These [verbatim identifiers](../../language-reference/tokens/verbatim.md) are primarily for interoperability with identifiers declared in other languages.</span></span>

<span data-ttu-id="62eb7-113">有关有效标识符的完整定义，请参阅 [C# 语言规范中的标识符主题](../../../../_csharplang/spec/lexical-structure.md#identifiers)。</span><span class="sxs-lookup"><span data-stu-id="62eb7-113">For a complete definition of valid identifiers, see the [Identifiers topic in the C# Language Specification](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="62eb7-114">命名约定</span><span class="sxs-lookup"><span data-stu-id="62eb7-114">Naming conventions</span></span>

<span data-ttu-id="62eb7-115">除了规则之外，在 .NET API 中还使用了许多标识符[命名约定](../../../standard/design-guidelines/naming-guidelines.md)。</span><span class="sxs-lookup"><span data-stu-id="62eb7-115">In addition to the rules, there are a number of identifier [naming conventions](../../../standard/design-guidelines/naming-guidelines.md) used throughout the .NET APIs.</span></span> <span data-ttu-id="62eb7-116">按照约定，C# 程序对类型名称、命名空间和所有公共成员使用 `PascalCase`。</span><span class="sxs-lookup"><span data-stu-id="62eb7-116">By convention, C# programs use `PascalCase` for type names, namespaces, and all public members.</span></span> <span data-ttu-id="62eb7-117">此外，以下约定也很常见：</span><span class="sxs-lookup"><span data-stu-id="62eb7-117">In addition, the following conventions are common:</span></span>

- <span data-ttu-id="62eb7-118">接口名称以大写字母 `I` 开头。</span><span class="sxs-lookup"><span data-stu-id="62eb7-118">Interface names start with a capital `I`.</span></span>
- <span data-ttu-id="62eb7-119">属性类型以单词 `Attribute` 结尾。</span><span class="sxs-lookup"><span data-stu-id="62eb7-119">Attribute types end with the word `Attribute`.</span></span>
- <span data-ttu-id="62eb7-120">枚举类型对非标记使用单数名词，对标记使用复数名词。</span><span class="sxs-lookup"><span data-stu-id="62eb7-120">Enum types use a singular noun for non-flags, and a plural noun for flags.</span></span>
- <span data-ttu-id="62eb7-121">标识符不应包含两个连续的 `_` 字符。</span><span class="sxs-lookup"><span data-stu-id="62eb7-121">Identifiers should not contain two consecutive `_` characters.</span></span> <span data-ttu-id="62eb7-122">这些名称保留给编译器生成的标识符。</span><span class="sxs-lookup"><span data-stu-id="62eb7-122">Those names are reserved for compiler generated identifiers.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="62eb7-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="62eb7-123">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="62eb7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="62eb7-124">See also</span></span>

- [<span data-ttu-id="62eb7-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="62eb7-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="62eb7-126">在 C# 程序内部</span><span class="sxs-lookup"><span data-stu-id="62eb7-126">Inside a C# Program</span></span>](../inside-a-program/index.md)
- [<span data-ttu-id="62eb7-127">C# 参考</span><span class="sxs-lookup"><span data-stu-id="62eb7-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="62eb7-128">类</span><span class="sxs-lookup"><span data-stu-id="62eb7-128">Classes</span></span>](../classes-and-structs/classes.md)
- [<span data-ttu-id="62eb7-129">结构</span><span class="sxs-lookup"><span data-stu-id="62eb7-129">Structs</span></span>](../classes-and-structs/structs.md)
- [<span data-ttu-id="62eb7-130">命名空间</span><span class="sxs-lookup"><span data-stu-id="62eb7-130">Namespaces</span></span>](../namespaces/index.md)
- [<span data-ttu-id="62eb7-131">接口</span><span class="sxs-lookup"><span data-stu-id="62eb7-131">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="62eb7-132">委托</span><span class="sxs-lookup"><span data-stu-id="62eb7-132">Delegates</span></span>](../delegates/index.md)
