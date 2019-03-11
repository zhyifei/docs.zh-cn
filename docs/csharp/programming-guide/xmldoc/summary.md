---
title: <summary> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 0e6408f1f45bb5f1406b4b1a7f6fe2cf543109e4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493565"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="79876-102">\<summary>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="79876-102">\<summary> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="79876-103">语法</span><span class="sxs-lookup"><span data-stu-id="79876-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="79876-104">参数</span><span class="sxs-lookup"><span data-stu-id="79876-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="79876-105">对象的摘要。</span><span class="sxs-lookup"><span data-stu-id="79876-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79876-106">备注</span><span class="sxs-lookup"><span data-stu-id="79876-106">Remarks</span></span>  
 <span data-ttu-id="79876-107">\<summary> 标记应当用于描述类型或类型成员。</span><span class="sxs-lookup"><span data-stu-id="79876-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="79876-108">使用 [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) 可针对某个类型说明添加补充信息。</span><span class="sxs-lookup"><span data-stu-id="79876-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="79876-109">使用 [cref 属性](../../../csharp/programming-guide/xmldoc/cref-attribute.md)可启用文档工具（如 [DocFX](https://dotnet.github.io/docfx/) 和 [Sandcastle](https://github.com/EWSoftware/SHFB)）来创建指向代码元素的文档页的内部超链接。</span><span class="sxs-lookup"><span data-stu-id="79876-109">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="79876-110">\<summary> 标记的文本是唯一有关 IntelliSense 中的类型的信息源，它也显示在对象浏览器窗口中。</span><span class="sxs-lookup"><span data-stu-id="79876-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="79876-111">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="79876-111">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="79876-112">若要基于编译器生成的文件创建最终文档，可以创建一个自定义工具，也可以使用 [DocFX](https://dotnet.github.io/docfx/) 或 [Sandcastle](https://github.com/EWSoftware/SHFB) 等工具。</span><span class="sxs-lookup"><span data-stu-id="79876-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79876-113">示例</span><span class="sxs-lookup"><span data-stu-id="79876-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
 <span data-ttu-id="79876-114">前面的示例生成下面的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="79876-114">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="example"></a><span data-ttu-id="79876-115">示例</span><span class="sxs-lookup"><span data-stu-id="79876-115">Example</span></span>  
 <span data-ttu-id="79876-116">下面的示例演示如何对泛型类型进行 `cref` 引用。</span><span class="sxs-lookup"><span data-stu-id="79876-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]  
  
 <span data-ttu-id="79876-117">前面的示例生成下面的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="79876-117">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79876-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="79876-118">See also</span></span>

- [<span data-ttu-id="79876-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="79876-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="79876-120">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="79876-120">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
