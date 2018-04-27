---
title: '&lt;消息&gt;此错误也可能是由于文件引用与程序集的项目引用混合使用&#39;&lt;程序集名称&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 37a152da06a36756b86576bad9c6c5d6a392dc8d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="5d5f5-102">&lt;消息&gt;此错误也可能是由于文件引用与程序集的项目引用混合使用&#39;&lt;程序集名称&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="5d5f5-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="5d5f5-103">\<消息 > 此错误也可能是由于混合文件引用与程序集的项目引用\<程序集名称 >。</span><span class="sxs-lookup"><span data-stu-id="5d5f5-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="5d5f5-104">在这种情况下，请尝试替换为对的文件引用\<assemblyfilename > 项目中\<projectname1 > 的项目引用与\<项目名称 2> >。</span><span class="sxs-lookup"><span data-stu-id="5d5f5-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="5d5f5-105">你的项目中的代码访问了另一个项目的成员，但你的解决方案配置不允许 Visual Basic 编译器来解析引用。</span><span class="sxs-lookup"><span data-stu-id="5d5f5-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="5d5f5-106">若要访问另一个程序集中定义的类型，Visual Basic 编译器必须具有对该程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="5d5f5-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="5d5f5-107">此引用必须单一、明确，不会导致项目之间循环引用。</span><span class="sxs-lookup"><span data-stu-id="5d5f5-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="5d5f5-108">**错误 ID：** BC30971</span><span class="sxs-lookup"><span data-stu-id="5d5f5-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5d5f5-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="5d5f5-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="5d5f5-110">确定产生最佳程序集引用的项目。</span><span class="sxs-lookup"><span data-stu-id="5d5f5-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="5d5f5-111">为便于确定，你可以使用文件访问轻松程度和更新频率等条件。</span><span class="sxs-lookup"><span data-stu-id="5d5f5-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="5d5f5-112">在项目属性中，添加对包含某程序集的项目的引用，该程序集定义正在使用的类型。</span><span class="sxs-lookup"><span data-stu-id="5d5f5-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d5f5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d5f5-113">See Also</span></span>  
 [<span data-ttu-id="5d5f5-114">管理项目中的引用</span><span class="sxs-lookup"><span data-stu-id="5d5f5-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="5d5f5-115">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="5d5f5-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [<span data-ttu-id="5d5f5-116">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="5d5f5-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="5d5f5-117">有关无效的引用的疑难解答</span><span class="sxs-lookup"><span data-stu-id="5d5f5-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
