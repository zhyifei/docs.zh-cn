---
title: XML 文档注释（C# 编程指南）
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: 4a8b6395209e95f3156354c4ee919291e05c7471
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998419"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="2d6d4-102">XML 文档注释（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2d6d4-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="2d6d4-103">在 Visual C# 中，你可以通过以下方式为代码创建文档：将特殊注释字段中的 XML 元素包含在源代码中注释引用的代码块的前面，例如：</span><span class="sxs-lookup"><span data-stu-id="2d6d4-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 <span data-ttu-id="2d6d4-104">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 选项进行编译时，编译器会在源代码中搜索所有 XML 标记，并创建一个 XML 文档文件。</span><span class="sxs-lookup"><span data-stu-id="2d6d4-104">When you compile with the [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="2d6d4-105">若要基于编译器生成的文件创建最终文档，可以创建一个自定义工具，也可以使用 [Sandcastle](https://github.com/EWSoftware/SHFB) 等工具。</span><span class="sxs-lookup"><span data-stu-id="2d6d4-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="2d6d4-106">若要引用 XML 元素（例如，你的函数将处理你要在 XML 文档注释中描述的特定 XML 元素），你可使用标准引用机制（`<` 和 `>`）。</span><span class="sxs-lookup"><span data-stu-id="2d6d4-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="2d6d4-107">若要引用代码引用 (`cref`) 元素中的通用标识符，可使用转义字符（例如，`cref="List&lt;T&gt;"`）或大括号 (`cref="List{T}"`)。</span><span class="sxs-lookup"><span data-stu-id="2d6d4-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="2d6d4-108">作为特例，编译器会将大括号解析为尖括号以在引用通用标识符时使作者能够更轻松地进行文档注释。</span><span class="sxs-lookup"><span data-stu-id="2d6d4-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d6d4-109">XML 文档注释不是元数据；它们不包括在编译的程序集中，因此无法通过反射对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="2d6d4-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d6d4-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="2d6d4-110">In This Section</span></span>  
  
-   [<span data-ttu-id="2d6d4-111">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="2d6d4-111">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="2d6d4-112">处理 XML 文件</span><span class="sxs-lookup"><span data-stu-id="2d6d4-112">Processing the XML File</span></span>](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="2d6d4-113">文档标记分隔符</span><span class="sxs-lookup"><span data-stu-id="2d6d4-113">Delimiters for Documentation Tags</span></span>](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [<span data-ttu-id="2d6d4-114">如何：使用 XML 文档功能</span><span class="sxs-lookup"><span data-stu-id="2d6d4-114">How to: Use the XML Documentation Features</span></span>](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a><span data-ttu-id="2d6d4-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="2d6d4-115">Related Sections</span></span>  
 <span data-ttu-id="2d6d4-116">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="2d6d4-116">For more information, see:</span></span>  
  
-   [<span data-ttu-id="2d6d4-117">/doc（处理文档注释）</span><span class="sxs-lookup"><span data-stu-id="2d6d4-117">/doc (Process Documentation Comments)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="2d6d4-118">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="2d6d4-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2d6d4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d6d4-119">See Also</span></span>  
 [<span data-ttu-id="2d6d4-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2d6d4-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
