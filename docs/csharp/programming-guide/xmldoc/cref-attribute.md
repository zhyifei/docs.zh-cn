---
title: cref 属性 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: af83ae8c6c209886649d4eb1543c47e63bd97449
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235576"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="ed817-102">cref 特性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ed817-102">cref Attribute (C# Programming Guide)</span></span>
<span data-ttu-id="ed817-103">XML 文档标记中的 `cref` 属性是指“代码引用”。</span><span class="sxs-lookup"><span data-stu-id="ed817-103">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="ed817-104">它指定标记的内部文本是一个代码元素，例如类型、方法或属性。</span><span class="sxs-lookup"><span data-stu-id="ed817-104">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="ed817-105">文档工具（例如 [Sandcastle](https://github.com/EWSoftware/SHFB)）使用 `cref` 属性自动生成指向记录类型或成员的页面的超链接。</span><span class="sxs-lookup"><span data-stu-id="ed817-105">Documentation tools like [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed817-106">示例</span><span class="sxs-lookup"><span data-stu-id="ed817-106">Example</span></span>  
 <span data-ttu-id="ed817-107">下面的示例演示了在 [\<see>](../../../csharp/programming-guide/xmldoc/see.md) 标记中使用的 `cref` 属性。</span><span class="sxs-lookup"><span data-stu-id="ed817-107">The following example shows `cref` attributes used in [\<see>](../../../csharp/programming-guide/xmldoc/see.md) tags.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#3](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/cref-attribute_1.cs)]  
  
 <span data-ttu-id="ed817-108">在编译时，该程序生成以下 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ed817-108">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="ed817-109">请注意，例如 `GetZero` 方法的 `cref` 属性已被编译器转换为 `"M:TestNamespace.TestClass.GetZero"`。</span><span class="sxs-lookup"><span data-stu-id="ed817-109">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="ed817-110">“M:”前缀表示“方法”，并且是一种由文档工具（例如 Sandcastle）识别的约定。</span><span class="sxs-lookup"><span data-stu-id="ed817-110">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as Sandcastle.</span></span> <span data-ttu-id="ed817-111">有关前缀的完整列表，请参阅[处理 XML 文件](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)。</span><span class="sxs-lookup"><span data-stu-id="ed817-111">For a complete list of prefixes, see [Processing the XML File](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md).</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>CRefTest</name>  
    </assembly>  
    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains cref examples.  
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
    </members>    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains two cref examples.  
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetZero">  
            <summary>  
            The GetZero method.  
            </summary>  
            <example> This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.  
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
  
## <a name="see-also"></a><span data-ttu-id="ed817-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed817-112">See Also</span></span>

- [<span data-ttu-id="ed817-113">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="ed817-113">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)  
- [<span data-ttu-id="ed817-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="ed817-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
