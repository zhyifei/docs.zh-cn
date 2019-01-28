---
title: 如何：使用 XML 文档功能 - C# 编程指南
ms.custom: seodec18
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 893dc726f7b4ee2d2afa69f63d13d1f11a4692db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491627"
---
# <a name="how-to-use-the-xml-documentation-features"></a><span data-ttu-id="8607f-102">如何：使用 XML 文档功能</span><span class="sxs-lookup"><span data-stu-id="8607f-102">How to: Use the XML documentation features</span></span>

<span data-ttu-id="8607f-103">下面的示例提供对某个已存档类型的基本概述。</span><span class="sxs-lookup"><span data-stu-id="8607f-103">The following sample provides a basic overview of a type that has been documented.</span></span>

## <a name="example"></a><span data-ttu-id="8607f-104">示例</span><span class="sxs-lookup"><span data-stu-id="8607f-104">Example</span></span>

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

<span data-ttu-id="8607f-105">该示例生成一个包含以下内容的 .xml 文件：</span><span class="sxs-lookup"><span data-stu-id="8607f-105">The example generates an .xml file with the following contents:</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member 
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a><span data-ttu-id="8607f-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="8607f-106">Compiling the code</span></span>

<span data-ttu-id="8607f-107">若要编译该示例，请键入以下命令行：</span><span class="sxs-lookup"><span data-stu-id="8607f-107">To compile the example, type the following command line:</span></span>

`csc XMLsample.cs /doc:XMLsample.xml`

<span data-ttu-id="8607f-108">此命令创建 XML 文件 XMLsample.xml，可在浏览器中或使用 TYPE 命令查看该文件。</span><span class="sxs-lookup"><span data-stu-id="8607f-108">This command creates the XML file *XMLsample.xml*, which you can view in your browser or by using the TYPE command.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="8607f-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="8607f-109">Robust programming</span></span>

<span data-ttu-id="8607f-110">XML 文档以 /// 开头。</span><span class="sxs-lookup"><span data-stu-id="8607f-110">XML documentation starts with ///.</span></span> <span data-ttu-id="8607f-111">创建新项目时，向导会放置一些以 /// 开头的行。</span><span class="sxs-lookup"><span data-stu-id="8607f-111">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="8607f-112">处理这些注释时存在一些限制：</span><span class="sxs-lookup"><span data-stu-id="8607f-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="8607f-113">文档必须是格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="8607f-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="8607f-114">如果 XML 格式不正确，则会生成警告，并且文档文件将包含一条注释，指出遇到错误。</span><span class="sxs-lookup"><span data-stu-id="8607f-114">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>

- <span data-ttu-id="8607f-115">开发人员可以随意创建自己的标记集。</span><span class="sxs-lookup"><span data-stu-id="8607f-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="8607f-116">推荐的标记集（请参阅[建议的文档注释标记](recommended-tags-for-documentation-comments.md)）。</span><span class="sxs-lookup"><span data-stu-id="8607f-116">There is a recommended set of tags (see [Recommended tags for documentation comments](recommended-tags-for-documentation-comments.md)).</span></span> <span data-ttu-id="8607f-117">部分建议标记具有特殊含义：</span><span class="sxs-lookup"><span data-stu-id="8607f-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="8607f-118">\<param> 标记用于描述参数。</span><span class="sxs-lookup"><span data-stu-id="8607f-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="8607f-119">如果已使用，编译器会验证该参数是否存在，以及文档是否描述了所有参数。</span><span class="sxs-lookup"><span data-stu-id="8607f-119">If used, the compiler verifies that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="8607f-120">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="8607f-120">If the verification failed, the compiler issues a warning.</span></span>

  - <span data-ttu-id="8607f-121">`cref` 属性可以附加到任何标记，以提供对代码元素的引用。</span><span class="sxs-lookup"><span data-stu-id="8607f-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="8607f-122">编译器验证此代码元素是否存在。</span><span class="sxs-lookup"><span data-stu-id="8607f-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="8607f-123">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="8607f-123">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="8607f-124">编译器在查找 `cref` 属性中描述的类型时会考虑所有 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="8607f-124">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="8607f-125">\<summary> 标记由 Visual Studio 中的 IntelliSense 用于显示有关某个类型或成员的附加信息。</span><span class="sxs-lookup"><span data-stu-id="8607f-125">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8607f-126">XML 文件不提供有关该类型和成员的完整信息（例如，它不包含任何类型信息）。</span><span class="sxs-lookup"><span data-stu-id="8607f-126">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="8607f-127">若要获取有关类型或成员的完整信息，必须将文档文件与对实际类型或成员的反射一起使用。</span><span class="sxs-lookup"><span data-stu-id="8607f-127">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>

## <a name="see-also"></a><span data-ttu-id="8607f-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="8607f-128">See also</span></span>

- [<span data-ttu-id="8607f-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8607f-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8607f-130">/doc（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="8607f-130">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="8607f-131">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="8607f-131">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
