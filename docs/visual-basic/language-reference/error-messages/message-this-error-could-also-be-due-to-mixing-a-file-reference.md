---
title: "&lt;消息&gt;此错误也可能是由于文件引用与程序集 &#39; 的项目引用混合使用&lt;assemblyname&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords: BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a30e5d5aca09e7b74e16dd05cdc0c5c361c1657d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="6569c-102">&lt;消息&gt;此错误也可能是由于文件引用与程序集 &#39; 的项目引用混合使用&lt;assemblyname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="6569c-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="6569c-103">\<消息 > 此错误也可能是由于混合文件引用与程序集的项目引用\<程序集名称 >。</span><span class="sxs-lookup"><span data-stu-id="6569c-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="6569c-104">在这种情况下，请尝试替换为对的文件引用\<assemblyfilename > 项目中\<projectname1 > 的项目引用与\<项目名称 2> >。</span><span class="sxs-lookup"><span data-stu-id="6569c-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="6569c-105">你项目中的代码访问了另一个项目的成员，但你的解决方案配置不允许使用 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器来解析引用。</span><span class="sxs-lookup"><span data-stu-id="6569c-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="6569c-106">若要访问另一个程序集中定义的类型， [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器必须具有对该程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="6569c-106">To access a type defined in another assembly, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="6569c-107">此引用必须单一、明确，不会导致项目之间循环引用。</span><span class="sxs-lookup"><span data-stu-id="6569c-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="6569c-108">**错误 ID：** BC30971</span><span class="sxs-lookup"><span data-stu-id="6569c-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6569c-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="6569c-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="6569c-110">确定产生最佳程序集引用的项目。</span><span class="sxs-lookup"><span data-stu-id="6569c-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="6569c-111">为便于确定，你可以使用文件访问轻松程度和更新频率等条件。</span><span class="sxs-lookup"><span data-stu-id="6569c-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="6569c-112">在项目属性中，添加对包含某程序集的项目的引用，该程序集定义正在使用的类型。</span><span class="sxs-lookup"><span data-stu-id="6569c-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6569c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6569c-113">See Also</span></span>  
 [<span data-ttu-id="6569c-114">管理项目中的引用</span><span class="sxs-lookup"><span data-stu-id="6569c-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="6569c-115">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="6569c-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="6569c-116">NIB 如何：使用“添加引用”对话框添加或删除引用</span><span class="sxs-lookup"><span data-stu-id="6569c-116">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [<span data-ttu-id="6569c-117">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="6569c-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="6569c-118">有关无效的引用的疑难解答</span><span class="sxs-lookup"><span data-stu-id="6569c-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
