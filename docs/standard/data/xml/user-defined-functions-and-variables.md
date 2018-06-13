---
title: 用户定义的函数和变量
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 4772f20e-1e7f-496e-93c2-1484473be555
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2ce474dac44de1ac72811ecd3bc294ba57ce40a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570448"
---
# <a name="user-defined-functions-and-variables"></a><span data-ttu-id="c3cdd-102">用户定义的函数和变量</span><span class="sxs-lookup"><span data-stu-id="c3cdd-102">User Defined Functions and Variables</span></span>
<span data-ttu-id="c3cdd-103"><xref:System.Xml.XPath.XPathNavigator> 类提供了一组方法，用于与 <xref:System.Xml.XPath.XPathDocument> 数据进行交互。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods that are used to interact with <xref:System.Xml.XPath.XPathDocument> data.</span></span> <span data-ttu-id="c3cdd-104">可以通过实现由 XPath 查询表达式使用的扩展函数和变量，对标准 XPath 函数进行补充。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-104">You can supplement the standard XPath functions by implementing extension functions and variables for use by XPath query expressions.</span></span> <span data-ttu-id="c3cdd-105"><xref:System.Xml.XPath.XPathExpression.SetContext%2A> 方法可以接受从 <xref:System.Xml.Xsl.XsltContext> 派生的用户定义的上下文。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-105">The <xref:System.Xml.XPath.XPathExpression.SetContext%2A> method can accept a user defined context derived from <xref:System.Xml.Xsl.XsltContext>.</span></span> <span data-ttu-id="c3cdd-106">用户定义的函数由自定义上下文解析。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-106">User defined functions are resolved by the custom context.</span></span>  
  
 <span data-ttu-id="c3cdd-107">扩展函数和变量有助于防范 XML 注入式攻击。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-107">Extension functions and variables can be useful in prevention of XML injection attacks.</span></span> <span data-ttu-id="c3cdd-108">在这些情况下，用户输入可分配给自定义变量，并由扩展函数进行处理，而不像通过处理指令串联的原始输入一样。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-108">In these scenarios user input is assigned to custom variables and processed by extension functions, not as raw input concatenated with processing instructions.</span></span> <span data-ttu-id="c3cdd-109">扩展函数和变量包含用户输入，因此它仅仅按照设计者的意图对 XML 数据进行操作。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-109">Extension functions and variables contain user input so that it only acts on XML data as intended by the designer.</span></span>  
  
 <span data-ttu-id="c3cdd-110">若要使用扩展，您需要实现一个自定义 <xref:System.Xml.Xsl.XsltContext> 类，以及用于支持扩展函数和变量的接口 <xref:System.Xml.Xsl.IXsltContextFunction> 和 <xref:System.Xml.Xsl.IXsltContextVariable>。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-110">To use extensions you implement a custom <xref:System.Xml.Xsl.XsltContext> class along with the interfaces <xref:System.Xml.Xsl.IXsltContextFunction> and <xref:System.Xml.Xsl.IXsltContextVariable> that support extension functions and variables.</span></span> <span data-ttu-id="c3cdd-111"><xref:System.Xml.XPath.XPathExpression> 通过其 <xref:System.Xml.Xsl.XsltArgumentList> 将用户输入添加到自定义 <xref:System.Xml.Xsl.XsltContext> 中。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-111">An <xref:System.Xml.XPath.XPathExpression> adds user input with its <xref:System.Xml.Xsl.XsltArgumentList> to the custom <xref:System.Xml.Xsl.XsltContext>.</span></span>  
  
 <span data-ttu-id="c3cdd-112"><xref:System.Xml.XPath.XPathExpression> 表示一个已编译的查询，<xref:System.Xml.XPath.XPathNavigator> 使用该查询来查找和处理由该表达式标识的节点。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-112">The <xref:System.Xml.XPath.XPathExpression> represents a compiled query that <xref:System.Xml.XPath.XPathNavigator> uses to find and process the nodes identified by the expression.</span></span>  
  
 <span data-ttu-id="c3cdd-113">下面的示例演示从 <xref:System.Xml.Xsl.XsltContext> 派生的自定义上下文类的实现。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-113">The following example shows implementation of a custom context class derived from <xref:System.Xml.Xsl.XsltContext>.</span></span> <span data-ttu-id="c3cdd-114">代码中的注释描述了类成员及其在自定义函数中的用法。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-114">Comments in the code describe class members and their use in custom functions.</span></span> <span data-ttu-id="c3cdd-115">这段代码之后还提供了函数和变量实现以及使用这些实现的示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-115">Function and variable implementations and a sample application that uses these implementations follow this code segment.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#2](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#2)]
 [!code-vb[XPathExtensionFunctions#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#2)]  
  
 <span data-ttu-id="c3cdd-116">下面的代码实现了 <xref:System.Xml.Xsl.IXsltContextFunction>。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-116">The following code implements <xref:System.Xml.Xsl.IXsltContextFunction>.</span></span> <span data-ttu-id="c3cdd-117">实现 <xref:System.Xml.Xsl.IXsltContextFunction> 的类将解析和执行用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-117">The class that implements <xref:System.Xml.Xsl.IXsltContextFunction> resolves and executes user-defined functions.</span></span> <span data-ttu-id="c3cdd-118">此示例使用此声明标识的函数：`private int CountChar(string title, char charTocount)`。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-118">This example uses the function identified by the declaration: `private int CountChar(string title, char charTocount)`.</span></span>  
  
 <span data-ttu-id="c3cdd-119">代码注释描述了类成员。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-119">Code comments describe class members.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#3](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#3)]
 [!code-vb[XPathExtensionFunctions#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#3)]  
  
 <span data-ttu-id="c3cdd-120">下面的代码实现了 <xref:System.Xml.Xsl.IXsltContextVariable>。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-120">The following code implements <xref:System.Xml.Xsl.IXsltContextVariable>.</span></span> <span data-ttu-id="c3cdd-121">此类在运行时解析 XPath 查询表达式中对用户定义的变量的引用。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-121">This class resolves references to user-defined variables in XPath query expressions at run time.</span></span> <span data-ttu-id="c3cdd-122">由自定义 <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A> 类的重写 <xref:System.Xml.Xsl.XsltContext> 方法创建并返回此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-122">An instance of this class is created and returned by the overridden <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A> method of the custom <xref:System.Xml.Xsl.XsltContext> class.</span></span>  
  
 <span data-ttu-id="c3cdd-123">代码注释描述了类成员。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-123">Code comments describe the class members.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#4](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#4)]
 [!code-vb[XPathExtensionFunctions#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#4)]  
  
 <span data-ttu-id="c3cdd-124">在前面的类定义的作用域内，下面的代码使用自定义函数来计算 `Tasks.xml` 文档的元素中的字符数。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-124">With the previous class definitions in scope, the following code uses the custom function to count characters in the elements of the `Tasks.xml` document.</span></span> <span data-ttu-id="c3cdd-125">代码中的注释描述了用于编译自定义函数并对 `Tasks.xml` 文档运行自定义函数的代码。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-125">Comments in the code describe the code that compiles the custom function and runs it against the `Tasks.xml` document.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#1](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#1)]
 [!code-vb[XPathExtensionFunctions#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#1)]  
  
 <span data-ttu-id="c3cdd-126">此示例使用下面的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="c3cdd-126">This example uses the following XML data.</span></span>  
  
 [!code-xml[XPathExtensionFunctions#5](../../../../samples/snippets/xml/VS_Snippets_Data/xpathextensionfunctions/XML/tasks.xml#5)]
