---
title: "如何：使用 XML 文档功能（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb647a275a5cd5fac2316706591440d9792861b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="69a69-102">如何：使用 XML 文档功能（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="69a69-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="69a69-103">下面的示例提供对某个已存档类型的基本概述。</span><span class="sxs-lookup"><span data-stu-id="69a69-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69a69-104">示例</span><span class="sxs-lookup"><span data-stu-id="69a69-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 <span data-ttu-id="69a69-105">**// This .xml file was generated with the previous code sample.**</span><span class="sxs-lookup"><span data-stu-id="69a69-105">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="69a69-106">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="69a69-106">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="69a69-107">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="69a69-107">**\<doc>**</span></span>  
 <span data-ttu-id="69a69-108">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="69a69-108">**\<assembly>**</span></span>  
 <span data-ttu-id="69a69-109">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="69a69-109">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="69a69-110">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="69a69-110">**\</assembly>**</span></span>  
 <span data-ttu-id="69a69-111">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="69a69-111">**\<members>**</span></span>  
 <span data-ttu-id="69a69-112">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="69a69-112">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="69a69-113">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-113">**\<summary>**</span></span>  
 <span data-ttu-id="69a69-114">**Class level summary documentation goes here.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-114">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="69a69-115">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="69a69-115">**\<remarks>**</span></span>  
 <span data-ttu-id="69a69-116">**较长的注释可以与类型或成员相关联**</span><span class="sxs-lookup"><span data-stu-id="69a69-116">**Longer comments can be associated with a type or member**</span></span>  
 <span data-ttu-id="69a69-117">**through the remarks tag\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="69a69-117">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="69a69-118">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="69a69-118">**\</member>**</span></span>  
 <span data-ttu-id="69a69-119">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="69a69-119">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="69a69-120">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-120">**\<summary>**</span></span>  
 <span data-ttu-id="69a69-121">**Store for the name property\</summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-121">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="69a69-122">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="69a69-122">**\</member>**</span></span>  
 <span data-ttu-id="69a69-123">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="69a69-123">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="69a69-124">**\<摘要 > 类构造函数。 \< /摘要 >**</span><span class="sxs-lookup"><span data-stu-id="69a69-124">**\<summary>The class constructor.\</summary>**</span></span>  
 <span data-ttu-id="69a69-125">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="69a69-125">**\</member>**</span></span>  
 <span data-ttu-id="69a69-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="69a69-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="69a69-127">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-127">**\<summary>**</span></span>  
 <span data-ttu-id="69a69-128">**Description for SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-128">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="69a69-129">**\<param name="s"> Parameter description for s goes here\</param>**</span><span class="sxs-lookup"><span data-stu-id="69a69-129">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="69a69-130">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="69a69-130">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="69a69-131">**可以使用任何标记上的 cref 特性来引用类型或成员**</span><span class="sxs-lookup"><span data-stu-id="69a69-131">**You can use the cref attribute on any tag to reference a type or member**</span></span>  
 <span data-ttu-id="69a69-132">**and the compiler will check that the reference exists. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="69a69-132">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="69a69-133">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="69a69-133">**\</member>**</span></span>  
 <span data-ttu-id="69a69-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="69a69-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="69a69-135">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-135">**\<summary>**</span></span>  
 <span data-ttu-id="69a69-136">**Some other method. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-136">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="69a69-137">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="69a69-137">**\<returns>**</span></span>  
 <span data-ttu-id="69a69-138">**Return results are described through the returns tag.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="69a69-138">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="69a69-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="69a69-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="69a69-140">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="69a69-140">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="69a69-141">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="69a69-141">**\</member>**</span></span>  
 <span data-ttu-id="69a69-142">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="69a69-142">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="69a69-143">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-143">**\<summary>**</span></span>  
 <span data-ttu-id="69a69-144">**The entry point for the application.**</span><span class="sxs-lookup"><span data-stu-id="69a69-144">**The entry point for the application.**</span></span>  
 <span data-ttu-id="69a69-145">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-145">**\</summary>**</span></span>  
 <span data-ttu-id="69a69-146">**\<param name="args"> A list of command line arguments\</param>**</span><span class="sxs-lookup"><span data-stu-id="69a69-146">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="69a69-147">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="69a69-147">**\</member>**</span></span>  
 <span data-ttu-id="69a69-148">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="69a69-148">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="69a69-149">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-149">**\<summary>**</span></span>  
 <span data-ttu-id="69a69-150">**Name property \</summary>**</span><span class="sxs-lookup"><span data-stu-id="69a69-150">**Name property \</summary>**</span></span>  
 <span data-ttu-id="69a69-151">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="69a69-151">**\<value>**</span></span>  
 <span data-ttu-id="69a69-152">**A value tag is used to describe the property value\</value>**</span><span class="sxs-lookup"><span data-stu-id="69a69-152">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="69a69-153">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="69a69-153">**\</member>**</span></span>  
 <span data-ttu-id="69a69-154">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="69a69-154">**\</members>**</span></span>  
<span data-ttu-id="69a69-155">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="69a69-155">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="69a69-156">编译代码</span><span class="sxs-lookup"><span data-stu-id="69a69-156">Compiling the Code</span></span>  
 <span data-ttu-id="69a69-157">若要编译该示例，请键入以下命令行：</span><span class="sxs-lookup"><span data-stu-id="69a69-157">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="69a69-158">这将创建 XML 文件 XMLsample.xml，可在浏览器中或使用 TYPE 命令查看该文件。</span><span class="sxs-lookup"><span data-stu-id="69a69-158">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="69a69-159">可靠编程</span><span class="sxs-lookup"><span data-stu-id="69a69-159">Robust Programming</span></span>  
 <span data-ttu-id="69a69-160">XML 文档以 /// 开头。</span><span class="sxs-lookup"><span data-stu-id="69a69-160">XML documentation starts with ///.</span></span> <span data-ttu-id="69a69-161">创建新项目时，向导会放置一些以 /// 开头的行。</span><span class="sxs-lookup"><span data-stu-id="69a69-161">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="69a69-162">处理这些注释时存在一些限制：</span><span class="sxs-lookup"><span data-stu-id="69a69-162">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="69a69-163">文档必须是格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="69a69-163">The documentation must be well-formed XML.</span></span> <span data-ttu-id="69a69-164">如果 XML 格式不正确，则会生成警告，并且文档文件将包含一条注释，指出遇到错误。</span><span class="sxs-lookup"><span data-stu-id="69a69-164">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="69a69-165">开发人员可以随意创建自己的标记集。</span><span class="sxs-lookup"><span data-stu-id="69a69-165">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="69a69-166">有建议的标记集（请参阅“更多参考资料”部分）。</span><span class="sxs-lookup"><span data-stu-id="69a69-166">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="69a69-167">部分建议标记具有特殊含义：</span><span class="sxs-lookup"><span data-stu-id="69a69-167">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="69a69-168">\<param> 标记用于描述参数。</span><span class="sxs-lookup"><span data-stu-id="69a69-168">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="69a69-169">如果使用，编译器将验证该参数是否存在，以及文档是否描述了所有参数。</span><span class="sxs-lookup"><span data-stu-id="69a69-169">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="69a69-170">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="69a69-170">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="69a69-171">`cref` 属性可以附加到任何标记，以提供对代码元素的引用。</span><span class="sxs-lookup"><span data-stu-id="69a69-171">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="69a69-172">编译器将验证此代码元素是否存在。</span><span class="sxs-lookup"><span data-stu-id="69a69-172">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="69a69-173">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="69a69-173">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="69a69-174">编译器在查找 `cref` 属性中描述的类型时会考虑所有 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="69a69-174">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="69a69-175">\<summary> 标记由 Visual Studio 中的 IntelliSense 用于显示有关某个类型或成员的附加信息。</span><span class="sxs-lookup"><span data-stu-id="69a69-175">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="69a69-176">XML 文件不提供有关该类型和成员的完整信息（例如，它不包含任何类型信息）。</span><span class="sxs-lookup"><span data-stu-id="69a69-176">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="69a69-177">若要获取有关类型或成员的完整信息，必须将文档文件与对实际类型或成员的反射一起使用。</span><span class="sxs-lookup"><span data-stu-id="69a69-177">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a69-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69a69-178">See Also</span></span>  
 [<span data-ttu-id="69a69-179">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="69a69-179">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="69a69-180">/doc （C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="69a69-180">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="69a69-181">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="69a69-181">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
