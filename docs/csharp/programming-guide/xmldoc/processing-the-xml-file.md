---
title: 处理 XML 文件 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
ms.openlocfilehash: bc72cade9ce6edddb88d741a3424405bba0a7ad8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793393"
---
# <a name="processing-the-xml-file-c-programming-guide"></a><span data-ttu-id="59931-102">处理 XML 文件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="59931-102">Processing the XML file (C# programming guide)</span></span>

<span data-ttu-id="59931-103">编译器为代码（已标记以生成文档）中的每个构造生成一个 ID 字符串。</span><span class="sxs-lookup"><span data-stu-id="59931-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="59931-104">（有关如何标记代码的信息，请参阅[文档注释的建议标记](./recommended-tags-for-documentation-comments.md)。）ID 字符串唯一标识构造。</span><span class="sxs-lookup"><span data-stu-id="59931-104">(For information about how to tag your code, see [Recommended Tags for Documentation Comments](./recommended-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="59931-105">处理 XML 文件的程序可以使用 ID 字符串来标识文档应用于的相应 .NET Framework 元数据/反射项目。</span><span class="sxs-lookup"><span data-stu-id="59931-105">Programs that process the XML file can use the ID string to identify the corresponding .NET Framework metadata/reflection item that the documentation applies to.</span></span>

<span data-ttu-id="59931-106">XML 文件不是代码的分层表示形式；它是具有每个元素生成的 ID 的简单列表。</span><span class="sxs-lookup"><span data-stu-id="59931-106">The XML file is not a hierarchical representation of your code; it is a flat list that has a generated ID for each element.</span></span>

<span data-ttu-id="59931-107">编译器在生成 ID 字符串时应遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="59931-107">The compiler observes the following rules when it generates the ID strings:</span></span>

- <span data-ttu-id="59931-108">字符串不得包含空白符。</span><span class="sxs-lookup"><span data-stu-id="59931-108">No white space is in the string.</span></span>

- <span data-ttu-id="59931-109">ID 字符串的第一部分标识被标识的成员类型，单个字符后跟一个冒号。</span><span class="sxs-lookup"><span data-stu-id="59931-109">The first part of the ID string identifies the kind of member being identified, by way of a single character followed by a colon.</span></span> <span data-ttu-id="59931-110">使用下面的成员类型：</span><span class="sxs-lookup"><span data-stu-id="59931-110">The following member types are used:</span></span>

    |<span data-ttu-id="59931-111">字符</span><span class="sxs-lookup"><span data-stu-id="59931-111">Character</span></span>|<span data-ttu-id="59931-112">描述</span><span class="sxs-lookup"><span data-stu-id="59931-112">Description</span></span>|
    |---------------|-----------------|
    |<span data-ttu-id="59931-113">N</span><span class="sxs-lookup"><span data-stu-id="59931-113">N</span></span>|<span data-ttu-id="59931-114">namespace</span><span class="sxs-lookup"><span data-stu-id="59931-114">namespace</span></span><br /><br /> <span data-ttu-id="59931-115">无法将文档注释添加到命名空间中，但可以在支持的情况下对它们进行 cref 引用。</span><span class="sxs-lookup"><span data-stu-id="59931-115">You cannot add documentation comments to a namespace, but you can make cref references to them, where supported.</span></span>|
    |<span data-ttu-id="59931-116">T</span><span class="sxs-lookup"><span data-stu-id="59931-116">T</span></span>|<span data-ttu-id="59931-117">类型：类、接口、结构、枚举或委托</span><span class="sxs-lookup"><span data-stu-id="59931-117">type: class, interface, struct, enum, or delegate</span></span>|
    |<span data-ttu-id="59931-118">F</span><span class="sxs-lookup"><span data-stu-id="59931-118">F</span></span>|<span data-ttu-id="59931-119">Field — 字段</span><span class="sxs-lookup"><span data-stu-id="59931-119">field</span></span>|
    |<span data-ttu-id="59931-120">P</span><span class="sxs-lookup"><span data-stu-id="59931-120">P</span></span>|<span data-ttu-id="59931-121">属性（包括索引器或其他的索引属性）</span><span class="sxs-lookup"><span data-stu-id="59931-121">property (including indexers or other indexed properties)</span></span>|
    |<span data-ttu-id="59931-122">M</span><span class="sxs-lookup"><span data-stu-id="59931-122">M</span></span>|<span data-ttu-id="59931-123">方法（包括构造函数、运算符等特殊方法）</span><span class="sxs-lookup"><span data-stu-id="59931-123">method (including such special methods as constructors, operators, and so forth)</span></span>|
    |<span data-ttu-id="59931-124">E</span><span class="sxs-lookup"><span data-stu-id="59931-124">E</span></span>|<span data-ttu-id="59931-125">event</span><span class="sxs-lookup"><span data-stu-id="59931-125">event</span></span>|
    |<span data-ttu-id="59931-126">!</span><span class="sxs-lookup"><span data-stu-id="59931-126">!</span></span>|<span data-ttu-id="59931-127">错误字符串</span><span class="sxs-lookup"><span data-stu-id="59931-127">error string</span></span><br /><br /> <span data-ttu-id="59931-128">字符串的其余部分提供有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="59931-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="59931-129">C# 编译器将生成无法解析的链接的错误信息。</span><span class="sxs-lookup"><span data-stu-id="59931-129">The C# compiler generates error information for links that cannot be resolved.</span></span>|

- <span data-ttu-id="59931-130">该字符串的第二部分是项目的完全限定名称，从命名空间的根开始。</span><span class="sxs-lookup"><span data-stu-id="59931-130">The second part of the string is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="59931-131">用句点分隔项目名称、其封闭类型和命名空间。</span><span class="sxs-lookup"><span data-stu-id="59931-131">The name of the item, its enclosing type(s), and namespace are separated by periods.</span></span> <span data-ttu-id="59931-132">如果项目名称本身包含句点，会将其替换为哈希符号 ('#')。</span><span class="sxs-lookup"><span data-stu-id="59931-132">If the name of the item itself has periods, they are replaced by the hash-sign ('#').</span></span> <span data-ttu-id="59931-133">假定没有名称中恰好包含哈希符号的项目。</span><span class="sxs-lookup"><span data-stu-id="59931-133">It is assumed that no item has a hash-sign directly in its name.</span></span> <span data-ttu-id="59931-134">例如，String 构造函数的完全限定名称将是“System.String.#ctor”。</span><span class="sxs-lookup"><span data-stu-id="59931-134">For example, the fully qualified name of the String constructor would be "System.String.#ctor".</span></span>

- <span data-ttu-id="59931-135">对于属性和方法，如果方法带有自变量，则后跟用括号括起来的自变量列表。</span><span class="sxs-lookup"><span data-stu-id="59931-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="59931-136">如果没有任何自变量，则不会出现括号。</span><span class="sxs-lookup"><span data-stu-id="59931-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="59931-137">确保自变量之间用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="59931-137">The arguments are separated by commas.</span></span> <span data-ttu-id="59931-138">每个自变量的编码直接遵循它在 .NET Framework 签名中的编码方式：</span><span class="sxs-lookup"><span data-stu-id="59931-138">The encoding of each argument follows directly how it is encoded in a .NET Framework signature:</span></span>

  - <span data-ttu-id="59931-139">基类型。</span><span class="sxs-lookup"><span data-stu-id="59931-139">Base types.</span></span> <span data-ttu-id="59931-140">常规的类型（ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE）表示为该类型的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="59931-140">Regular types (ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE) are represented as the fully qualified name of the type.</span></span>

  - <span data-ttu-id="59931-141">内部类型（例如，ELEMENT_TYPE_I4、ELEMENT_TYPE_OBJECT、ELEMENT_TYPE_STRING、ELEMENT_TYPE_TYPEDBYREF 和 ELEMENT_TYPE_VOID）表示为相应完整类型的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="59931-141">Intrinsic types (for example, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF, and ELEMENT_TYPE_VOID) are represented as the fully qualified name of the corresponding full type.</span></span> <span data-ttu-id="59931-142">例如，System.Int32 或 System.TypedReference。</span><span class="sxs-lookup"><span data-stu-id="59931-142">For example, System.Int32 or System.TypedReference.</span></span>

  - <span data-ttu-id="59931-143">ELEMENT_TYPE_PTR 表示为修改类型之后的“\*”。</span><span class="sxs-lookup"><span data-stu-id="59931-143">ELEMENT_TYPE_PTR is represented as a '\*' following the modified type.</span></span>

  - <span data-ttu-id="59931-144">ELEMENT_TYPE_BYREF 表示为修改类型之后的“\@”。</span><span class="sxs-lookup"><span data-stu-id="59931-144">ELEMENT_TYPE_BYREF is represented as a '\@' following the modified type.</span></span>

  - <span data-ttu-id="59931-145">ELEMENT_TYPE_PINNED 表示为修改类型之后的“^”。</span><span class="sxs-lookup"><span data-stu-id="59931-145">ELEMENT_TYPE_PINNED is represented as a '^' following the modified type.</span></span> <span data-ttu-id="59931-146">C# 编译器不会生成此类型。</span><span class="sxs-lookup"><span data-stu-id="59931-146">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="59931-147">ELEMENT_TYPE_CMOD_REQ 表示为“&#124;”和修饰符类的完全限定名称，前面是修改类型。</span><span class="sxs-lookup"><span data-stu-id="59931-147">ELEMENT_TYPE_CMOD_REQ is represented as a '&#124;' and the fully qualified name of the modifier class, following the modified type.</span></span> <span data-ttu-id="59931-148">C# 编译器不会生成此类型。</span><span class="sxs-lookup"><span data-stu-id="59931-148">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="59931-149">ELEMENT_TYPE_CMOD_OPT 表示为“!”和修饰符类的完全限定名称，前面是修改类型。</span><span class="sxs-lookup"><span data-stu-id="59931-149">ELEMENT_TYPE_CMOD_OPT is represented as a '!' and the fully qualified name of the modifier class, following the modified type.</span></span>

  - <span data-ttu-id="59931-150">ELEMENT_TYPE_SZARRAY 表示为“[]”，前面是数组的元素类型。</span><span class="sxs-lookup"><span data-stu-id="59931-150">ELEMENT_TYPE_SZARRAY is represented as "[]" following the element type of the array.</span></span>

  - <span data-ttu-id="59931-151">ELEMENT_TYPE_GENERICARRAY 表示为“[?]”，前面是数组的元素类型。</span><span class="sxs-lookup"><span data-stu-id="59931-151">ELEMENT_TYPE_GENERICARRAY is represented as "[?]" following the element type of the array.</span></span> <span data-ttu-id="59931-152">C# 编译器不会生成此类型。</span><span class="sxs-lookup"><span data-stu-id="59931-152">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="59931-153">ELEMENT_TYPE_ARRAY 表示为 [*lowerbound*:`size`,*lowerbound*:`size`]，其中逗号的数量是秩 - 1，每个维度的下限和大小（如果已知）以十进制形式表示。</span><span class="sxs-lookup"><span data-stu-id="59931-153">ELEMENT_TYPE_ARRAY is represented as [*lowerbound*:`size`,*lowerbound*:`size`] where the number of commas is the rank - 1, and the lower bounds and size of each dimension, if known, are represented in decimal.</span></span> <span data-ttu-id="59931-154">如果未指定下限或大小，则只需将其省略。</span><span class="sxs-lookup"><span data-stu-id="59931-154">If a lower bound or size is not specified, it is simply omitted.</span></span> <span data-ttu-id="59931-155">如果省略某个特定维度的下限和大小，也会省略“:”。</span><span class="sxs-lookup"><span data-stu-id="59931-155">If the lower bound and size for a particular dimension are omitted, the ':' is omitted as well.</span></span> <span data-ttu-id="59931-156">例如，以 1 作为下限并且未指定大小的二维数组是 [1:,1:]。</span><span class="sxs-lookup"><span data-stu-id="59931-156">For example, a 2-dimensional array with 1 as the lower bounds and unspecified sizes is [1:,1:].</span></span>

  - <span data-ttu-id="59931-157">ELEMENT_TYPE_FNPTR 表示为“=FUNC:`type`(*signature*)”，其中 `type` 是返回类型，*signature* 是方法的自变量。</span><span class="sxs-lookup"><span data-stu-id="59931-157">ELEMENT_TYPE_FNPTR is represented as "=FUNC:`type`(*signature*)", where `type` is the return type, and *signature* is the arguments of the method.</span></span> <span data-ttu-id="59931-158">如果没有任何自变量，则省略括号。</span><span class="sxs-lookup"><span data-stu-id="59931-158">If there are no arguments, the parentheses are omitted.</span></span> <span data-ttu-id="59931-159">C# 编译器不会生成此类型。</span><span class="sxs-lookup"><span data-stu-id="59931-159">The C# compiler never generates this.</span></span>

    <span data-ttu-id="59931-160">不表示下列签名组件，因为它们永远不会用于区分重载方法：</span><span class="sxs-lookup"><span data-stu-id="59931-160">The following signature components are not represented because they are never used for differentiating overloaded methods:</span></span>

  - <span data-ttu-id="59931-161">调用约定</span><span class="sxs-lookup"><span data-stu-id="59931-161">calling convention</span></span>

  - <span data-ttu-id="59931-162">返回类型</span><span class="sxs-lookup"><span data-stu-id="59931-162">return type</span></span>

  - <span data-ttu-id="59931-163">ELEMENT_TYPE_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="59931-163">ELEMENT_TYPE_SENTINEL</span></span>

- <span data-ttu-id="59931-164">仅适用于转换运算符（op_Implicit 和 op_Explicit），该方法的返回值被编码为“~”，后面是返回类型，如上面的编码所示。</span><span class="sxs-lookup"><span data-stu-id="59931-164">For conversion operators only (op_Implicit and op_Explicit), the return value of the method is encoded as a '~' followed by the return type, as encoded above.</span></span>

- <span data-ttu-id="59931-165">对于泛型类型，类型名称后跟反引号，然后是指示泛型类型参数数量的一个数字。</span><span class="sxs-lookup"><span data-stu-id="59931-165">For generic types, the name of the type is followed by a backtick and then a number that indicates the number of generic type parameters.</span></span> <span data-ttu-id="59931-166">例如：</span><span class="sxs-lookup"><span data-stu-id="59931-166">For example:</span></span>

     <span data-ttu-id="59931-167">``<member name="T:SampleClass`2">`` 是定义为 `public class SampleClass<T, U>` 的类型的标记。</span><span class="sxs-lookup"><span data-stu-id="59931-167">``<member name="T:SampleClass`2">`` is the tag for a type that is defined as `public class SampleClass<T, U>`.</span></span>

     <span data-ttu-id="59931-168">对于将泛型类型用作参数的方法，泛型类型参数被指定为前面加上反引号的数字（例如 \`0、\`1）。</span><span class="sxs-lookup"><span data-stu-id="59931-168">For methods taking generic types as parameters, the generic type parameters are specified as numbers prefaced with backticks (for example \`0,\`1).</span></span> <span data-ttu-id="59931-169">每个数字表示该类型的泛型参数的从零开始的数组表示法。</span><span class="sxs-lookup"><span data-stu-id="59931-169">Each number representing a zero-based array notation for the type's generic parameters.</span></span>

## <a name="examples"></a><span data-ttu-id="59931-170">示例</span><span class="sxs-lookup"><span data-stu-id="59931-170">Examples</span></span>

<span data-ttu-id="59931-171">下面的示例演示如何为类及其成员生成 ID 字符串：</span><span class="sxs-lookup"><span data-stu-id="59931-171">The following examples show how the ID strings for a class and its members would be generated:</span></span>

[!code-csharp[csProgGuidePointers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#21)]

## <a name="see-also"></a><span data-ttu-id="59931-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="59931-172">See also</span></span>

- [<span data-ttu-id="59931-173">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="59931-173">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="59931-174">-doc（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="59931-174">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="59931-175">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="59931-175">XML documentation comments</span></span>](./index.md)
