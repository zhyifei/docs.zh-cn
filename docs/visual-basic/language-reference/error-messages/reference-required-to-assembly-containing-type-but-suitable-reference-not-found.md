---
title: "需要引用程序集 &quot;&lt;assemblyidentity&gt;包含类型&lt;typename&gt;，但由于语意不明确的项目之间找不到合适的引用&lt;projectname1&gt;&quot;和&quot;&lt;projectname2&gt;&quot; |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
dev_langs:
- VB
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bb5375366fa525a0ca9c16944d026ca499062ed8
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a><span data-ttu-id="9f51d-102">需要引用程序集 '&lt;assemblyidentity&gt;包含类型&lt;typename&gt;，但由于语意不明确的项目之间找不到合适的引用&lt;projectname1&gt;'和'&lt;projectname2&gt;</span><span class="sxs-lookup"><span data-stu-id="9f51d-102">Reference required to assembly &#39;&lt;assemblyidentity&gt;&#39; containing type &#39;&lt;typename&gt;&#39;, but a suitable reference could not be found due to ambiguity between projects &#39;&lt;projectname1&gt;&#39; and &#39;&lt;projectname2&gt;&#39;</span></span>
<span data-ttu-id="9f51d-103">表达式使用在项目外部定义的类型，如类、结构、接口、枚举或委托。</span><span class="sxs-lookup"><span data-stu-id="9f51d-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="9f51d-104">但是，你具有对定义该类型的多个程序集的项目引用。</span><span class="sxs-lookup"><span data-stu-id="9f51d-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="9f51d-105">引用的项目会生成名称相同的程序集。</span><span class="sxs-lookup"><span data-stu-id="9f51d-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="9f51d-106">因此，编译器无法确定对要访问的类型使用哪一个程序集。</span><span class="sxs-lookup"><span data-stu-id="9f51d-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="9f51d-107">若要访问其他程序集中定义的类型[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器必须具有对该程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9f51d-107">To access a type defined in another assembly, the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="9f51d-108">此引用必须单一、明确，不会导致项目之间循环引用。</span><span class="sxs-lookup"><span data-stu-id="9f51d-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="9f51d-109">**错误 ID：** BC30969</span><span class="sxs-lookup"><span data-stu-id="9f51d-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9f51d-110">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9f51d-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="9f51d-111">确定产生最佳程序集引用的项目。</span><span class="sxs-lookup"><span data-stu-id="9f51d-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="9f51d-112">为便于确定，你可以使用文件访问轻松程度和更新频率等条件。</span><span class="sxs-lookup"><span data-stu-id="9f51d-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="9f51d-113">在项目属性中，添加对包含某程序集的文件的引用，该程序集定义正在使用的类型。</span><span class="sxs-lookup"><span data-stu-id="9f51d-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f51d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f51d-114">See Also</span></span>  
 <span data-ttu-id="9f51d-115">[管理项目中引用](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="9f51d-115">[Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="9f51d-116"> [对已声明的元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="9f51d-116"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="9f51d-117"> [NIB 如何：使用“添加引用”对话框添加或删除引用](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="9f51d-117"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="9f51d-118"> [NIB 如何︰ 修改项目属性和配置设置](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="9f51d-118"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="9f51d-119"> [有关无效的引用的疑难解答](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span><span class="sxs-lookup"><span data-stu-id="9f51d-119"> [Troubleshooting Broken References](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span></span>
