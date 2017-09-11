---
title: "需要引用程序集 &quot;&lt;assemblyname&gt;包含基类&lt;classname&gt;&quot; |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
dev_langs:
- VB
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
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
ms.openlocfilehash: 131f8fd53fe025ac16450d9ff0019626444c6cc6
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a><span data-ttu-id="b79e1-102">需要引用程序集 '&lt;assemblyname&gt;包含基类&lt;classname&gt;</span><span class="sxs-lookup"><span data-stu-id="b79e1-102">Reference required to assembly &#39;&lt;assemblyname&gt;&#39; containing the base class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="b79e1-103">需要引用程序集 '\<程序集名称&1;> 包含基类\<classname&1;>。</span><span class="sxs-lookup"><span data-stu-id="b79e1-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="b79e1-104">请向项目中添加一个。</span><span class="sxs-lookup"><span data-stu-id="b79e1-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="b79e1-105">该类是在动态链接库 (DLL) 或未在项目中直接引用的程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="b79e1-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="b79e1-106">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器需要一个引用，以避免多义性的类定义在多个 DLL 或程序集。</span><span class="sxs-lookup"><span data-stu-id="b79e1-106">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="b79e1-107">**错误 ID：** BC30007</span><span class="sxs-lookup"><span data-stu-id="b79e1-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b79e1-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b79e1-108">To correct this error</span></span>  
  
-   <span data-ttu-id="b79e1-109">将未引用的 DLL 或程序集名称包括在项目引用中。</span><span class="sxs-lookup"><span data-stu-id="b79e1-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79e1-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b79e1-110">See Also</span></span>  
 <span data-ttu-id="b79e1-111">[NIB 如何：使用“添加引用”对话框添加或删除引用](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="b79e1-111">[NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="b79e1-112"> [管理项目中引用](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="b79e1-112"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="b79e1-113"> [有关无效的引用的疑难解答](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span><span class="sxs-lookup"><span data-stu-id="b79e1-113"> [Troubleshooting Broken References](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span></span>
