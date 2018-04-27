---
title: 需要对程序集的引用&#39; &lt;assemblyname&gt; &#39;包含基类&#39;&lt;类名&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6dd53e2d0bf0535de50e465293edb26a5b1d484
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a><span data-ttu-id="82cfb-102">需要对程序集的引用&#39; &lt;assemblyname&gt; &#39;包含基类&#39;&lt;类名&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="82cfb-102">Reference required to assembly &#39;&lt;assemblyname&gt;&#39; containing the base class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="82cfb-103">需要引用程序集\<程序集名称 > 包含基类的\<类名 >。</span><span class="sxs-lookup"><span data-stu-id="82cfb-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="82cfb-104">请向项目中添加一个。</span><span class="sxs-lookup"><span data-stu-id="82cfb-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="82cfb-105">该类是在动态链接库 (DLL) 或未在项目中直接引用的程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="82cfb-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="82cfb-106">Visual Basic 编译器需要引用以避免多义性类定义在多个 DLL 或程序集。</span><span class="sxs-lookup"><span data-stu-id="82cfb-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="82cfb-107">**错误 ID：** BC30007</span><span class="sxs-lookup"><span data-stu-id="82cfb-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="82cfb-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="82cfb-108">To correct this error</span></span>  
  
-   <span data-ttu-id="82cfb-109">将未引用的 DLL 或程序集名称包括在项目引用中。</span><span class="sxs-lookup"><span data-stu-id="82cfb-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82cfb-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="82cfb-110">See Also</span></span>  
   
 [<span data-ttu-id="82cfb-111">管理项目中的引用</span><span class="sxs-lookup"><span data-stu-id="82cfb-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="82cfb-112">有关无效的引用的疑难解答</span><span class="sxs-lookup"><span data-stu-id="82cfb-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
