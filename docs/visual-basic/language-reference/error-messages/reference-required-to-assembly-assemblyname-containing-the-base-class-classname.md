---
title: 需要对程序集的引用&#39; &lt;assemblyname&gt; &#39;包含基类&#39;&lt;类名&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: f2aa8f1f05ce15bd25992b7f1851854952108813
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506261"
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>需要对程序集的引用&#39; &lt;assemblyname&gt; &#39;包含基类&#39;&lt;类名&gt;&#39;
需要对程序集的引用\<程序集名称 > 包含基类的\<类名 >。 请向项目中添加一个。  
  
 该类是在动态链接库 (DLL) 或未在项目中直接引用的程序集中定义的。 Visual Basic 编译器需要引用以避免多义性的类定义在多个 DLL 或程序集。  
  
 **错误 ID:** BC30007  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   将未引用的 DLL 或程序集名称包括在项目引用中。  
  
## <a name="see-also"></a>请参阅

- [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)
- [有关无效的引用的疑难解答](/visualstudio/ide/troubleshooting-broken-references)
