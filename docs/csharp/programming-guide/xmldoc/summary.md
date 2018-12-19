---
title: '&lt;summary&gt; - C# 编程指南'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 5aaa9b08b422c06cc6b009e5e9d781e8be46af7e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237293"
---
# <a name="ltsummarygt-c-programming-guide"></a><span data-ttu-id="f5a49-102">&lt;summary&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f5a49-102">&lt;summary&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f5a49-103">语法</span><span class="sxs-lookup"><span data-stu-id="f5a49-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5a49-104">参数</span><span class="sxs-lookup"><span data-stu-id="f5a49-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="f5a49-105">对象的摘要。</span><span class="sxs-lookup"><span data-stu-id="f5a49-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5a49-106">备注</span><span class="sxs-lookup"><span data-stu-id="f5a49-106">Remarks</span></span>  
 <span data-ttu-id="f5a49-107">\<summary> 标记应当用于描述类型或类型成员。</span><span class="sxs-lookup"><span data-stu-id="f5a49-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="f5a49-108">使用 [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) 可针对某个类型说明添加补充信息。</span><span class="sxs-lookup"><span data-stu-id="f5a49-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="f5a49-109">使用 [cref 属性](../../../csharp/programming-guide/xmldoc/cref-attribute.md)可启用文档工具（如 [Sandcastle](https://github.com/EWSoftware/SHFB)）来创建指向代码元素的文档页的内部超链接。</span><span class="sxs-lookup"><span data-stu-id="f5a49-109">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to enable documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="f5a49-110">\<summary> 标记的文本是唯一有关 IntelliSense 中的类型的信息源，它也显示在对象浏览器窗口中。</span><span class="sxs-lookup"><span data-stu-id="f5a49-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="f5a49-111">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="f5a49-111">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="f5a49-112">若要基于编译器生成的文件创建最终文档，可以创建一个自定义工具，也可以使用 [Sandcastle](https://github.com/EWSoftware/SHFB) 等工具。</span><span class="sxs-lookup"><span data-stu-id="f5a49-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5a49-113">示例</span><span class="sxs-lookup"><span data-stu-id="f5a49-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 <span data-ttu-id="f5a49-114">前面的示例生成下面的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="f5a49-114">The previous example produces the following XML file.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="f5a49-115">示例</span><span class="sxs-lookup"><span data-stu-id="f5a49-115">Example</span></span>  
 <span data-ttu-id="f5a49-116">下面的示例演示如何对泛型类型进行 `cref` 引用。</span><span class="sxs-lookup"><span data-stu-id="f5a49-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 <span data-ttu-id="f5a49-117">前面的示例生成下面的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="f5a49-117">The previous example produces the following XML file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f5a49-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5a49-118">See Also</span></span>

- [<span data-ttu-id="f5a49-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f5a49-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f5a49-120">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="f5a49-120">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
