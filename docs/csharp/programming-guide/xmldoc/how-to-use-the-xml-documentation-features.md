---
title: "如何：使用 XML 文档功能（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
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
ms.openlocfilehash: eeee77db523bc0ad97f425d4ba8076ae5740dfe8
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="5df8c-102">如何：使用 XML 文档功能（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5df8c-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="5df8c-103">下面的示例提供对某个已存档类型的基本概述。</span><span class="sxs-lookup"><span data-stu-id="5df8c-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5df8c-104">示例</span><span class="sxs-lookup"><span data-stu-id="5df8c-104">Example</span></span>  
 <span data-ttu-id="5df8c-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5df8c-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span></span>  
  
 <span data-ttu-id="5df8c-106">**// This .xml file was generated with the previous code sample.**</span><span class="sxs-lookup"><span data-stu-id="5df8c-106">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="5df8c-107">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-107">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="5df8c-108">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-108">**\<doc>**</span></span>  
 <span data-ttu-id="5df8c-109">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-109">**\<assembly>**</span></span>  
 <span data-ttu-id="5df8c-110">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-110">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="5df8c-111">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-111">**\</assembly>**</span></span>  
 <span data-ttu-id="5df8c-112">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-112">**\<members>**</span></span>  
 <span data-ttu-id="5df8c-113">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="5df8c-113">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="5df8c-114">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-114">**\<summary>**</span></span>  
 <span data-ttu-id="5df8c-115">**Class level summary documentation goes here.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-115">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="5df8c-116">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-116">**\<remarks>**</span></span>  
 <span data-ttu-id="5df8c-117">**Longer comments can be associated with a type or member** </span><span class="sxs-lookup"><span data-stu-id="5df8c-117">**Longer comments can be associated with a type or member** </span></span>  
 <span data-ttu-id="5df8c-118">**through the remarks tag\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-118">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="5df8c-119">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-119">**\</member>**</span></span>  
 <span data-ttu-id="5df8c-120">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="5df8c-120">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="5df8c-121">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-121">**\<summary>**</span></span>  
 <span data-ttu-id="5df8c-122">**Store for the name property\</summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-122">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="5df8c-123">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-123">**\</member>**</span></span>  
 <span data-ttu-id="5df8c-124">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="5df8c-124">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="5df8c-125">**\<summary>The class constructor.\</summary>** </span><span class="sxs-lookup"><span data-stu-id="5df8c-125">**\<summary>The class constructor.\</summary>** </span></span>  
 <span data-ttu-id="5df8c-126">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-126">**\</member>**</span></span>  
 <span data-ttu-id="5df8c-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="5df8c-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="5df8c-128">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-128">**\<summary>**</span></span>  
 <span data-ttu-id="5df8c-129">**Description for SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-129">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="5df8c-130">**\<param name="s"> Parameter description for s goes here\</param>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-130">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="5df8c-131">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="5df8c-131">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="5df8c-132">**You can use the cref attribute on any tag to reference a type or member** </span><span class="sxs-lookup"><span data-stu-id="5df8c-132">**You can use the cref attribute on any tag to reference a type or member** </span></span>  
 <span data-ttu-id="5df8c-133">**and the compiler will check that the reference exists. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-133">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="5df8c-134">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-134">**\</member>**</span></span>  
 <span data-ttu-id="5df8c-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="5df8c-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="5df8c-136">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-136">**\<summary>**</span></span>  
 <span data-ttu-id="5df8c-137">**Some other method. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-137">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="5df8c-138">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-138">**\<returns>**</span></span>  
 <span data-ttu-id="5df8c-139">**Return results are described through the returns tag.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-139">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="5df8c-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="5df8c-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="5df8c-141">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-141">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="5df8c-142">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-142">**\</member>**</span></span>  
 <span data-ttu-id="5df8c-143">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="5df8c-143">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="5df8c-144">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-144">**\<summary>**</span></span>  
 <span data-ttu-id="5df8c-145">**The entry point for the application.**</span><span class="sxs-lookup"><span data-stu-id="5df8c-145">**The entry point for the application.**</span></span>  
 <span data-ttu-id="5df8c-146">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-146">**\</summary>**</span></span>  
 <span data-ttu-id="5df8c-147">**\<param name="args"> A list of command line arguments\</param>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-147">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="5df8c-148">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-148">**\</member>**</span></span>  
 <span data-ttu-id="5df8c-149">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="5df8c-149">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="5df8c-150">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-150">**\<summary>**</span></span>  
 <span data-ttu-id="5df8c-151">**Name property \</summary>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-151">**Name property \</summary>**</span></span>  
 <span data-ttu-id="5df8c-152">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-152">**\<value>**</span></span>  
 <span data-ttu-id="5df8c-153">**A value tag is used to describe the property value\</value>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-153">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="5df8c-154">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-154">**\</member>**</span></span>  
 <span data-ttu-id="5df8c-155">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-155">**\</members>**</span></span>  
<span data-ttu-id="5df8c-156">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="5df8c-156">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="5df8c-157">编译代码</span><span class="sxs-lookup"><span data-stu-id="5df8c-157">Compiling the Code</span></span>  
 <span data-ttu-id="5df8c-158">若要编译该示例，请键入以下命令行：</span><span class="sxs-lookup"><span data-stu-id="5df8c-158">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="5df8c-159">这将创建 XML 文件 XMLsample.xml，可在浏览器中或使用 TYPE 命令查看该文件。</span><span class="sxs-lookup"><span data-stu-id="5df8c-159">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5df8c-160">可靠编程</span><span class="sxs-lookup"><span data-stu-id="5df8c-160">Robust Programming</span></span>  
 <span data-ttu-id="5df8c-161">XML 文档以 /// 开头。</span><span class="sxs-lookup"><span data-stu-id="5df8c-161">XML documentation starts with ///.</span></span> <span data-ttu-id="5df8c-162">创建新项目时，向导会放置一些以 /// 开头的行。</span><span class="sxs-lookup"><span data-stu-id="5df8c-162">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="5df8c-163">处理这些注释时存在一些限制：</span><span class="sxs-lookup"><span data-stu-id="5df8c-163">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="5df8c-164">文档必须是格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="5df8c-164">The documentation must be well-formed XML.</span></span> <span data-ttu-id="5df8c-165">如果 XML 格式不正确，则会生成警告，并且文档文件将包含一条注释，指出遇到错误。</span><span class="sxs-lookup"><span data-stu-id="5df8c-165">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="5df8c-166">开发人员可以随意创建自己的标记集。</span><span class="sxs-lookup"><span data-stu-id="5df8c-166">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="5df8c-167">有建议的标记集（请参阅“更多参考资料”部分）。</span><span class="sxs-lookup"><span data-stu-id="5df8c-167">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="5df8c-168">部分建议标记具有特殊含义：</span><span class="sxs-lookup"><span data-stu-id="5df8c-168">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="5df8c-169">\<param> 标记用于描述参数。</span><span class="sxs-lookup"><span data-stu-id="5df8c-169">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="5df8c-170">如果使用，编译器将验证该参数是否存在，以及文档是否描述了所有参数。</span><span class="sxs-lookup"><span data-stu-id="5df8c-170">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="5df8c-171">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="5df8c-171">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="5df8c-172">`cref` 属性可以附加到任何标记，以提供对代码元素的引用。</span><span class="sxs-lookup"><span data-stu-id="5df8c-172">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="5df8c-173">编译器将验证此代码元素是否存在。</span><span class="sxs-lookup"><span data-stu-id="5df8c-173">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="5df8c-174">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="5df8c-174">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="5df8c-175">编译器在查找 `cref` 属性中描述的类型时会考虑所有 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="5df8c-175">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="5df8c-176">\<summary> 标记由 Visual Studio 中的 IntelliSense 用于显示有关某个类型或成员的附加信息。</span><span class="sxs-lookup"><span data-stu-id="5df8c-176">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5df8c-177">XML 文件不提供有关该类型和成员的完整信息（例如，它不包含任何类型信息）。</span><span class="sxs-lookup"><span data-stu-id="5df8c-177">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="5df8c-178">若要获取有关类型或成员的完整信息，必须将文档文件与对实际类型或成员的反射一起使用。</span><span class="sxs-lookup"><span data-stu-id="5df8c-178">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df8c-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="5df8c-179">See Also</span></span>  
 <span data-ttu-id="5df8c-180">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5df8c-180">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5df8c-181">[/doc（C# 编译器选项）](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="5df8c-181">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="5df8c-182">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="5df8c-182">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

