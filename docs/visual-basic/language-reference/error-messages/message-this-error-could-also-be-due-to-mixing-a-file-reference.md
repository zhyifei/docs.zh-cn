---
title: '&lt;消息&gt;此错误也可能是由于文件引用与程序集的项目引用混合使用&#39;&lt;程序集名称&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 498ca74497077e3268aa8cb25ce5121f3c9ea59d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;消息&gt;此错误也可能是由于文件引用与程序集的项目引用混合使用&#39;&lt;程序集名称&gt;&#39;
\<消息 > 此错误也可能是由于混合文件引用与程序集的项目引用\<程序集名称 >。 在这种情况下，请尝试替换为对的文件引用\<assemblyfilename > 项目中\<projectname1 > 的项目引用与\<项目名称 2> >。  
  
 你的项目中的代码访问了另一个项目的成员，但你的解决方案配置不允许 Visual Basic 编译器来解析引用。  
  
 若要访问另一个程序集中定义的类型，Visual Basic 编译器必须具有对该程序集的引用。 此引用必须单一、明确，不会导致项目之间循环引用。  
  
 **错误 ID：** BC30971  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确定产生最佳程序集引用的项目。 为便于确定，你可以使用文件访问轻松程度和更新频率等条件。  
  
2.  在项目属性中，添加对包含某程序集的项目的引用，该程序集定义正在使用的类型。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)  
 [对已声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [管理项目和解决方案属性](/visualstudio/ide/managing-project-and-solution-properties)  
 [有关无效的引用的疑难解答](/visualstudio/ide/troubleshooting-broken-references)
