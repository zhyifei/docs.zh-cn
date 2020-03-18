---
title: cref 属性 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: b06d0c9d447124dec7d8cf3c0cbbfd0daca78fe3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79157008"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="05057-102">cref 属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="05057-102">cref attribute (C# programming guide)</span></span>

<span data-ttu-id="05057-103">XML 文档标记中的 `cref` 属性是指“代码引用”。</span><span class="sxs-lookup"><span data-stu-id="05057-103">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="05057-104">它指定标记的内部文本是一个代码元素，例如类型、方法或属性。</span><span class="sxs-lookup"><span data-stu-id="05057-104">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="05057-105">文档工具（例如 [DocFX](https://dotnet.github.io/docfx/) 和 [Sandcastle](https://github.com/EWSoftware/SHFB)）使用 `cref` 属性自动生成指向记录类型或成员的页面的超链接。</span><span class="sxs-lookup"><span data-stu-id="05057-105">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>

## <a name="example"></a><span data-ttu-id="05057-106">示例</span><span class="sxs-lookup"><span data-stu-id="05057-106">Example</span></span>

<span data-ttu-id="05057-107">下面的示例演示了在 `cref`[see>\< 标记中使用的 ](./see.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="05057-107">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

<span data-ttu-id="05057-108">在编译时，该程序生成以下 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="05057-108">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="05057-109">请注意，例如 `cref` 方法的 `GetZero` 属性已被编译器转换为 `"M:TestNamespace.TestClass.GetZero"`。</span><span class="sxs-lookup"><span data-stu-id="05057-109">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="05057-110">“M:”前缀表示“方法”，并且是一种由文档工具（例如 DocFX 和 Sandcastle）识别的约定。</span><span class="sxs-lookup"><span data-stu-id="05057-110">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="05057-111">有关前缀的完整列表，请参阅[处理 XML 文件](./processing-the-xml-file.md)。</span><span class="sxs-lookup"><span data-stu-id="05057-111">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>

```xml  
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:TestNamespace.TestClass">
            <summary>
            TestClass contains several cref examples.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor">
            <summary>
            This sample shows how to specify the <see cref="T:TestNamespace.TestClass"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor(System.Int32)">
            <summary>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.#ctor(System.Int32)"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.GetZero">
            <summary>
            The GetZero method.
            </summary>
            <example>
            This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.
            <code>
            class TestClass
            {
                static int Main()
                {
                    return GetZero();
                }
            }
            </code>
            </example>
        </member>
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">
            <summary>
            The GetGenericValue method.
            </summary>
            <remarks>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.
            </remarks>
        </member>
        <member name="T:TestNamespace.GenericClass`1">
            <summary>
            GenericClass.
            </summary>
            <remarks>
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.
            </remarks>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="05057-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05057-112">See also</span></span>

- [<span data-ttu-id="05057-113">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="05057-113">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="05057-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="05057-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
