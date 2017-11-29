---
title: "需要对程序集 &#39; 的引用&lt;assemblyname&gt;&#39; 包含基类 &#39;&lt;类名&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords: BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7413c82a9c61d13e7ca6fa18f27a4769a0937f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>需要对程序集 &#39; 的引用&lt;assemblyname&gt;&#39; 包含基类 &#39;&lt;类名&gt;&#39;
需要引用程序集\<程序集名称 > 包含基类的\<类名 >。 请向项目中添加一个。  
  
 该类是在动态链接库 (DLL) 或未在项目中直接引用的程序集中定义的。 如果该类是在多个 DLL 或程序集中定义的，则 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器需要引用以避免多义性。  
  
 **错误 ID：** BC30007  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   将未引用的 DLL 或程序集名称包括在项目引用中。  
  
## <a name="see-also"></a>另请参阅  
 [NIB 如何：使用“添加引用”对话框添加或删除引用](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)  
 [有关无效的引用的疑难解答](/visualstudio/ide/troubleshooting-broken-references)
