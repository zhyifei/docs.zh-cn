---
title: "需要对程序集 &#39; 的引用&lt;assemblyidentity&gt;&#39; 包含类型 &#39;&lt;typename&gt;&#39;，但由于语意不明确之间项目 &#39; 找不到合适的引用&lt;projectname1&gt;&#39; 和 &#39;&lt;项目名称 2>&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords: BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 04a1b16a10d2a3945d1efbe3a2bd0850f1da39fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a>需要对程序集 &#39; 的引用&lt;assemblyidentity&gt;&#39; 包含类型 &#39;&lt;typename&gt;&#39;，但由于语意不明确之间项目 &#39; 找不到合适的引用&lt;projectname1&gt;&#39; 和 &#39;&lt;项目名称 2>&gt;&#39;
表达式使用在项目外部定义的类型，如类、结构、接口、枚举或委托。 但是，你具有对定义该类型的多个程序集的项目引用。  
  
 引用的项目会生成名称相同的程序集。 因此，编译器无法确定对要访问的类型使用哪一个程序集。  
  
 若要访问另一个程序集中定义的类型， [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器必须具有对该程序集的引用。 此引用必须单一、明确，不会导致项目之间循环引用。  
  
 **错误 ID：** BC30969  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确定产生最佳程序集引用的项目。 为便于确定，你可以使用文件访问轻松程度和更新频率等条件。  
  
2.  在项目属性中，添加对包含某程序集的文件的引用，该程序集定义正在使用的类型。  
  
## <a name="see-also"></a>另请参阅  
 [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)  
 [对已声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [NIB 如何：使用“添加引用”对话框添加或删除引用](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [管理项目和解决方案属性](/visualstudio/ide/managing-project-and-solution-properties)  
 [有关无效的引用的疑难解答](/visualstudio/ide/troubleshooting-broken-references)
