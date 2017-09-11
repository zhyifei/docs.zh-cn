---
title: "处理 XML 文件（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 610f3ac5c88fb41a4b55f2990fecdc4c13074e19
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="processing-the-xml-file-c-programming-guide"></a><span data-ttu-id="d3d01-102">处理 XML 文件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="d3d01-102">Processing the XML File (C# Programming Guide)</span></span>
<span data-ttu-id="d3d01-103">编译器为代码（已标记以生成文档）中的每个构造生成一个 ID 字符串。</span><span class="sxs-lookup"><span data-stu-id="d3d01-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="d3d01-104">（有关如何标记代码的信息，请参阅[文档注释的建议标记](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)。）ID 字符串唯一标识构造。</span><span class="sxs-lookup"><span data-stu-id="d3d01-104">(For information about how to tag your code, see [Recommended Tags for Documentation Comments](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="d3d01-105">处理 XML 文件的程序可以使用 ID 字符串来标识文档应用于的相应 .NET Framework 元数据/反射项目。</span><span class="sxs-lookup"><span data-stu-id="d3d01-105">Programs that process the XML file can use the ID string to identify the corresponding .NET Framework metadata/reflection item that the documentation applies to.</span></span>  
  
 <span data-ttu-id="d3d01-106">XML 文件不是代码的分层表示形式；它是具有每个元素生成的 ID 的简单列表。</span><span class="sxs-lookup"><span data-stu-id="d3d01-106">The XML file is not a hierarchical representation of your code; it is a flat list that has a generated ID for each element.</span></span>  
  
 <span data-ttu-id="d3d01-107">编译器在生成 ID 字符串时应遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="d3d01-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="d3d01-108">字符串中没有空格。</span><span class="sxs-lookup"><span data-stu-id="d3d01-108">No whitespace is in the string.</span></span>  
  
-   <span data-ttu-id="d3d01-109">ID 字符串的第一部分标识被标识的成员类型，单个字符后跟一个冒号。</span><span class="sxs-lookup"><span data-stu-id="d3d01-109">The first part of the ID string identifies the kind of member being identified, by way of a single character followed by a colon.</span></span> <span data-ttu-id="d3d01-110">使用下面的成员类型：</span><span class="sxs-lookup"><span data-stu-id="d3d01-110">The following member types are used:</span></span>  
  
    |<span data-ttu-id="d3d01-111">字符</span><span class="sxs-lookup"><span data-stu-id="d3d01-111">Character</span></span>|<span data-ttu-id="d3d01-112">描述</span><span class="sxs-lookup"><span data-stu-id="d3d01-112">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="d3d01-113">N</span><span class="sxs-lookup"><span data-stu-id="d3d01-113">N</span></span>|<span data-ttu-id="d3d01-114">namespace</span><span class="sxs-lookup"><span data-stu-id="d3d01-114">namespace</span></span><br /><br /> <span data-ttu-id="d3d01-115">无法将文档注释添加到命名空间中，但可以在支持的情况下对它们进行 cref 引用。</span><span class="sxs-lookup"><span data-stu-id="d3d01-115">You cannot add documentation comments to a namespace, but you can make cref references to them, where supported.</span></span>|  
    |<span data-ttu-id="d3d01-116">T</span><span class="sxs-lookup"><span data-stu-id="d3d01-116">T</span></span>|<span data-ttu-id="d3d01-117">类型：类、接口、结构、枚举、委托</span><span class="sxs-lookup"><span data-stu-id="d3d01-117">type: class, interface, struct, enum, delegate</span></span>|  
    |<span data-ttu-id="d3d01-118">F</span><span class="sxs-lookup"><span data-stu-id="d3d01-118">F</span></span>|<span data-ttu-id="d3d01-119">Field — 字段</span><span class="sxs-lookup"><span data-stu-id="d3d01-119">field</span></span>|  
    |<span data-ttu-id="d3d01-120">P</span><span class="sxs-lookup"><span data-stu-id="d3d01-120">P</span></span>|<span data-ttu-id="d3d01-121">属性（包括索引器或其他的索引属性）</span><span class="sxs-lookup"><span data-stu-id="d3d01-121">property (including indexers or other indexed properties)</span></span>|  
    |<span data-ttu-id="d3d01-122">M</span><span class="sxs-lookup"><span data-stu-id="d3d01-122">M</span></span>|<span data-ttu-id="d3d01-123">方法（包括构造函数、运算符等特殊方法）</span><span class="sxs-lookup"><span data-stu-id="d3d01-123">method (including such special methods as constructors, operators, and so forth)</span></span>|  
    |<span data-ttu-id="d3d01-124">E</span><span class="sxs-lookup"><span data-stu-id="d3d01-124">E</span></span>|<span data-ttu-id="d3d01-125">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="d3d01-125">event</span></span>|  
    |<span data-ttu-id="d3d01-126">!</span><span class="sxs-lookup"><span data-stu-id="d3d01-126">!</span></span>|<span data-ttu-id="d3d01-127">错误字符串</span><span class="sxs-lookup"><span data-stu-id="d3d01-127">error string</span></span><br /><br /> <span data-ttu-id="d3d01-128">字符串的其余部分提供有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d3d01-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="d3d01-129">C# 编译器将生成无法解析的链接的错误信息。</span><span class="sxs-lookup"><span data-stu-id="d3d01-129">The C# compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="d3d01-130">该字符串的第二部分是项目的完全限定名称，从命名空间的根开始。</span><span class="sxs-lookup"><span data-stu-id="d3d01-130">The second part of the string is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="d3d01-131">用句点分隔项目名称、其封闭类型和命名空间。</span><span class="sxs-lookup"><span data-stu-id="d3d01-131">The name of the item, its enclosing type(s), and namespace are separated by periods.</span></span> <span data-ttu-id="d3d01-132">如果项目名称本身包含句点，会将其替换为哈希符号 ('#')。</span><span class="sxs-lookup"><span data-stu-id="d3d01-132">If the name of the item itself has periods, they are replaced by the hash-sign ('#').</span></span> <span data-ttu-id="d3d01-133">假定没有名称中恰好包含哈希符号的项目。</span><span class="sxs-lookup"><span data-stu-id="d3d01-133">It is assumed that no item has a hash-sign directly in its name.</span></span> <span data-ttu-id="d3d01-134">例如，String 构造函数的完全限定名称将是“System.String.#ctor”。</span><span class="sxs-lookup"><span data-stu-id="d3d01-134">For example, the fully qualified name of the String constructor would be "System.String.#ctor".</span></span>  
  
-   <span data-ttu-id="d3d01-135">对于属性和方法，如果方法带有自变量，则后跟用括号括起来的自变量列表。</span><span class="sxs-lookup"><span data-stu-id="d3d01-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="d3d01-136">如果没有任何自变量，则不会出现括号。</span><span class="sxs-lookup"><span data-stu-id="d3d01-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="d3d01-137">确保自变量之间用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="d3d01-137">The arguments are separated by commas.</span></span> <span data-ttu-id="d3d01-138">每个自变量的编码直接遵循它在 .NET Framework 签名中的编码方式：</span><span class="sxs-lookup"><span data-stu-id="d3d01-138">The encoding of each argument follows directly how it is encoded in a .NET Framework signature:</span></span>  
  
    -   <span data-ttu-id="d3d01-139">基类型。</span><span class="sxs-lookup"><span data-stu-id="d3d01-139">Base types.</span></span> <span data-ttu-id="d3d01-140">常规的类型（ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE）表示为该类型的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="d3d01-140">Regular types (ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE) are represented as the fully qualified name of the type.</span></span>  
  
    -   <span data-ttu-id="d3d01-141">内部类型（例如，ELEMENT_TYPE_I4、ELEMENT_TYPE_OBJECT、ELEMENT_TYPE_STRING、ELEMENT_TYPE_TYPEDBYREF</span><span class="sxs-lookup"><span data-stu-id="d3d01-141">Intrinsic types (for example, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF.</span></span> <span data-ttu-id="d3d01-142">和 ELEMENT_TYPE_VOID）表示为对应的完整类型的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="d3d01-142">and ELEMENT_TYPE_VOID) are represented as the fully qualified name of the corresponding full type.</span></span> <span data-ttu-id="d3d01-143">例如，System.Int32 或 System.TypedReference。</span><span class="sxs-lookup"><span data-stu-id="d3d01-143">For example, System.Int32 or System.TypedReference.</span></span>  
  
    -   <span data-ttu-id="d3d01-144">ELEMENT_TYPE_PTR 表示为修改类型之后的“*”。</span><span class="sxs-lookup"><span data-stu-id="d3d01-144">ELEMENT_TYPE_PTR is represented as a '*' following the modified type.</span></span>  
  
    -   <span data-ttu-id="d3d01-145">ELEMENT_TYPE_BYREF 表示为修改类型之后的“@”。</span><span class="sxs-lookup"><span data-stu-id="d3d01-145">ELEMENT_TYPE_BYREF is represented as a '@' following the modified type.</span></span>  
  
    -   <span data-ttu-id="d3d01-146">ELEMENT_TYPE_PINNED 表示为修改类型之后的“^”。</span><span class="sxs-lookup"><span data-stu-id="d3d01-146">ELEMENT_TYPE_PINNED is represented as a '^' following the modified type.</span></span> <span data-ttu-id="d3d01-147">C# 编译器不会生成此类型。</span><span class="sxs-lookup"><span data-stu-id="d3d01-147">The C# compiler never generates this.</span></span>  
  
    -   <span data-ttu-id="d3d01-148">ELEMENT_TYPE_CMOD_REQ 表示为“&#124;”和修饰符类的完全限定名称，前面是修改类型。</span><span class="sxs-lookup"><span data-stu-id="d3d01-148">ELEMENT_TYPE_CMOD_REQ is represented as a '&#124;' and the fully qualified name of the modifier class, following the modified type.</span></span> <span data-ttu-id="d3d01-149">C# 编译器不会生成此类型。</span><span class="sxs-lookup"><span data-stu-id="d3d01-149">The C# compiler never generates this.</span></span>  
  
    -   <span data-ttu-id="d3d01-150">ELEMENT_TYPE_CMOD_OPT 表示为“!”和修饰符类的完全限定名称，前面是修改类型。</span><span class="sxs-lookup"><span data-stu-id="d3d01-150">ELEMENT_TYPE_CMOD_OPT is represented as a '!' and the fully qualified name of the modifier class, following the modified type.</span></span>  
  
    -   <span data-ttu-id="d3d01-151">ELEMENT_TYPE_SZARRAY 表示为“[]”，前面是数组的元素类型。</span><span class="sxs-lookup"><span data-stu-id="d3d01-151">ELEMENT_TYPE_SZARRAY is represented as "[]" following the element type of the array.</span></span>  
  
    -   <span data-ttu-id="d3d01-152">ELEMENT_TYPE_GENERICARRAY 表示为“[?]”，前面是数组的元素类型。</span><span class="sxs-lookup"><span data-stu-id="d3d01-152">ELEMENT_TYPE_GENERICARRAY is represented as "[?]" following the element type of the array.</span></span> <span data-ttu-id="d3d01-153">C# 编译器不会生成此类型。</span><span class="sxs-lookup"><span data-stu-id="d3d01-153">The C# compiler never generates this.</span></span>  
  
    -   <span data-ttu-id="d3d01-154">ELEMENT_TYPE_ARRAY 表示为 [*lowerbound*:`size`,*lowerbound*:`size`]，其中逗号的数量是秩 - 1，每个维度的下限和大小（如果已知）以十进制形式表示。</span><span class="sxs-lookup"><span data-stu-id="d3d01-154">ELEMENT_TYPE_ARRAY is represented as [*lowerbound*:`size`,*lowerbound*:`size`] where the number of commas is the rank - 1, and the lower bounds and size of each dimension, if known, are represented in decimal.</span></span> <span data-ttu-id="d3d01-155">如果未指定下限或大小，则只需将其省略。</span><span class="sxs-lookup"><span data-stu-id="d3d01-155">If a lower bound or size is not specified, it is simply omitted.</span></span> <span data-ttu-id="d3d01-156">如果省略某个特定维度的下限和大小，也会省略“:”。</span><span class="sxs-lookup"><span data-stu-id="d3d01-156">If the lower bound and size for a particular dimension are omitted, the ':' is omitted as well.</span></span> <span data-ttu-id="d3d01-157">例如，以 1 作为下限并且未指定大小的二维数组是 [1:,1:]。</span><span class="sxs-lookup"><span data-stu-id="d3d01-157">For example, a 2-dimensional array with 1 as the lower bounds and unspecified sizes is [1:,1:].</span></span>  
  
    -   <span data-ttu-id="d3d01-158">ELEMENT_TYPE_FNPTR 表示为“=FUNC:`type`(*signature*)”，其中 `type` 是返回类型，*signature* 是方法的自变量。</span><span class="sxs-lookup"><span data-stu-id="d3d01-158">ELEMENT_TYPE_FNPTR is represented as "=FUNC:`type`(*signature*)", where `type` is the return type, and *signature* is the arguments of the method.</span></span> <span data-ttu-id="d3d01-159">如果没有任何自变量，则省略括号。</span><span class="sxs-lookup"><span data-stu-id="d3d01-159">If there are no arguments, the parentheses are omitted.</span></span> <span data-ttu-id="d3d01-160">C# 编译器不会生成此类型。</span><span class="sxs-lookup"><span data-stu-id="d3d01-160">The C# compiler never generates this.</span></span>  
  
     <span data-ttu-id="d3d01-161">不表示下列签名组件，因为它们永远不会用于区分重载方法：</span><span class="sxs-lookup"><span data-stu-id="d3d01-161">The following signature components are not represented because they are never used for differentiating overloaded methods:</span></span>  
  
    -   <span data-ttu-id="d3d01-162">调用约定</span><span class="sxs-lookup"><span data-stu-id="d3d01-162">calling convention</span></span>  
  
    -   <span data-ttu-id="d3d01-163">返回类型</span><span class="sxs-lookup"><span data-stu-id="d3d01-163">return type</span></span>  
  
    -   <span data-ttu-id="d3d01-164">ELEMENT_TYPE_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="d3d01-164">ELEMENT_TYPE_SENTINEL</span></span>  
  
-   <span data-ttu-id="d3d01-165">仅适用于转换运算符（op_Implicit 和 op_Explicit），该方法的返回值被编码为“~”，后面是返回类型，如上面的编码所示。</span><span class="sxs-lookup"><span data-stu-id="d3d01-165">For conversion operators only (op_Implicit and op_Explicit), the return value of the method is encoded as a '~' followed by the return type, as encoded above.</span></span>  
  
-   <span data-ttu-id="d3d01-166">对于泛型类型，类型名称后跟反勾号，然后是指示泛型类型参数数量的一个数字。</span><span class="sxs-lookup"><span data-stu-id="d3d01-166">For generic types, the name of the type will be followed by a back tick and then a number that indicates the number of generic type parameters.</span></span>  <span data-ttu-id="d3d01-167">例如，</span><span class="sxs-lookup"><span data-stu-id="d3d01-167">For example,</span></span>  
  
     <span data-ttu-id="d3d01-168">`<member name="T:SampleClass`2">` is the tag for a type that is defined as `public class SampleClass\<T, U>\`.</span><span class="sxs-lookup"><span data-stu-id="d3d01-168">`<member name="T:SampleClass`2">` is the tag for a type that is defined as `public class SampleClass\<T, U>\`.</span></span>  
  
     <span data-ttu-id="d3d01-169">对于将泛型类型用作参数的方法，泛型类型参数被指定为前面加上反勾号的数字（例如 \`0,`1）。</span><span class="sxs-lookup"><span data-stu-id="d3d01-169">For methods taking generic types as parameters, the generic type parameters are specified as numbers prefaced with back ticks (for example \`0,`1).</span></span>  <span data-ttu-id="d3d01-170">每个数字表示该类型的泛型参数的从零开始的数组表示法。</span><span class="sxs-lookup"><span data-stu-id="d3d01-170">Each number representing a zero-based array notation for the type's generic parameters.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d3d01-171">示例</span><span class="sxs-lookup"><span data-stu-id="d3d01-171">Examples</span></span>  
 <span data-ttu-id="d3d01-172">下面的示例演示如何为类及其成员生成 ID 字符串：</span><span class="sxs-lookup"><span data-stu-id="d3d01-172">The following examples show how the ID strings for a class and its members would be generated:</span></span>  
  
 <span data-ttu-id="d3d01-173">[!code-cs[csProgGuidePointers#21](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/processing-the-xml-file_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3d01-173">[!code-cs[csProgGuidePointers#21](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/processing-the-xml-file_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d01-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3d01-174">See Also</span></span>  
 <span data-ttu-id="d3d01-175">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d3d01-175">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d3d01-176">[/doc（C# 编译器选项）](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="d3d01-176">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="d3d01-177">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="d3d01-177">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

