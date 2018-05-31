---
title: 如何：使用 XML 文档功能（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: d7f1f51040033cf25f7f1aefb04d249e6e028ca3
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472771"
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="10959-102">如何：使用 XML 文档功能（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="10959-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="10959-103">下面的示例提供对某个已存档类型的基本概述。</span><span class="sxs-lookup"><span data-stu-id="10959-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10959-104">示例</span><span class="sxs-lookup"><span data-stu-id="10959-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  

<span data-ttu-id="10959-105">该示例生成一个包含以下内容的 .xml 文件：</span><span class="sxs-lookup"><span data-stu-id="10959-105">The example generates an .xml file with the following contents:</span></span>

```xml  
<?xml version="1.0"?>  
<doc>  
 <assembly>  
 <name>xmlsample</name>  
 </assembly>  
 <members>  
 <member name="T:SomeClass">  
 <summary>  
 Class level summary documentation goes here.</summary>  
 <remarks>  
 Longer comments can be associated with a type or member  
 through the remarks tag</remarks>  
 </member>  
 <member name="F:SomeClass.m_Name">  
 <summary>  
 Store for the name property</summary>  
 </member>  
 <member name="M:SomeClass.#ctor">  
 <summary>The class constructor.</summary>  
 </member>  
 <member name="M:SomeClass.SomeMethod(System.String)">  
 <summary>  
 Description for SomeMethod.</summary>  
 <param name="s"> Parameter description for s goes here</param>  
 <seealso cref="T:System.String">  
 You can use the cref attribute on any tag to reference a type or member  
 and the compiler will check that the reference exists. </seealso>  
 </member>  
 <member name="M:SomeClass.SomeOtherMethod">  
 <summary>  
 Some other method. </summary>  
 <returns>  
 Return results are described through the returns tag.</returns>  
 <seealso cref="M:SomeClass.SomeMethod(System.String)">  
 Notice the use of the cref attribute to reference a specific method </seealso>  
 </member>  
 <member name="M:SomeClass.Main(System.String[])">  
 <summary>  
 The entry point for the application.  
 </summary>  
 <param name="args"> A list of command line arguments</param>  
 </member>  
 <member name="P:SomeClass.Name">  
 <summary>  
 Name property </summary>  
 <value>A value tag is used to describe the property value</value>  
 </member>  
 </members>  
</doc>   
```

## <a name="compiling-the-code"></a><span data-ttu-id="10959-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="10959-106">Compiling the Code</span></span>  
 <span data-ttu-id="10959-107">若要编译该示例，请键入以下命令行：</span><span class="sxs-lookup"><span data-stu-id="10959-107">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="10959-108">这将创建 XML 文件 XMLsample.xml，可在浏览器中或使用 TYPE 命令查看该文件。</span><span class="sxs-lookup"><span data-stu-id="10959-108">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="10959-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="10959-109">Robust Programming</span></span>  
 <span data-ttu-id="10959-110">XML 文档以 /// 开头。</span><span class="sxs-lookup"><span data-stu-id="10959-110">XML documentation starts with ///.</span></span> <span data-ttu-id="10959-111">创建新项目时，向导会放置一些以 /// 开头的行。</span><span class="sxs-lookup"><span data-stu-id="10959-111">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="10959-112">处理这些注释时存在一些限制：</span><span class="sxs-lookup"><span data-stu-id="10959-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="10959-113">文档必须是格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="10959-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="10959-114">如果 XML 格式不正确，则会生成警告，并且文档文件将包含一条注释，指出遇到错误。</span><span class="sxs-lookup"><span data-stu-id="10959-114">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="10959-115">开发人员可以随意创建自己的标记集。</span><span class="sxs-lookup"><span data-stu-id="10959-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="10959-116">推荐的标记集（请参阅[建议的文档注释标记](recommended-tags-for-documentation-comments.md)）。</span><span class="sxs-lookup"><span data-stu-id="10959-116">There is a recommended set of tags (see [Recommended tags for documentation comments](recommended-tags-for-documentation-comments.md)).</span></span> <span data-ttu-id="10959-117">部分建议标记具有特殊含义：</span><span class="sxs-lookup"><span data-stu-id="10959-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="10959-118">\<param> 标记用于描述参数。</span><span class="sxs-lookup"><span data-stu-id="10959-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="10959-119">如果使用，编译器将验证该参数是否存在，以及文档是否描述了所有参数。</span><span class="sxs-lookup"><span data-stu-id="10959-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="10959-120">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="10959-120">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="10959-121">`cref` 属性可以附加到任何标记，以提供对代码元素的引用。</span><span class="sxs-lookup"><span data-stu-id="10959-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="10959-122">编译器将验证此代码元素是否存在。</span><span class="sxs-lookup"><span data-stu-id="10959-122">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="10959-123">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="10959-123">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="10959-124">编译器在查找 `cref` 属性中描述的类型时会考虑所有 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="10959-124">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="10959-125">\<summary> 标记由 Visual Studio 中的 IntelliSense 用于显示有关某个类型或成员的附加信息。</span><span class="sxs-lookup"><span data-stu-id="10959-125">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="10959-126">XML 文件不提供有关该类型和成员的完整信息（例如，它不包含任何类型信息）。</span><span class="sxs-lookup"><span data-stu-id="10959-126">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="10959-127">若要获取有关类型或成员的完整信息，必须将文档文件与对实际类型或成员的反射一起使用。</span><span class="sxs-lookup"><span data-stu-id="10959-127">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10959-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="10959-128">See Also</span></span>  
 [<span data-ttu-id="10959-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="10959-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="10959-130">/doc（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="10959-130">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="10959-131">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="10959-131">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
