---
title: 需要对程序集“<assemblyname>”（包含基类“<classname>”）的引用
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 8218a3325d5d47bf85aacab1724221d233d92ba4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661695"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>需要对程序集的引用\<程序集名称 > 包含基类的\<类名 >'
需要对程序集的引用\<程序集名称 > 包含基类的\<类名 >。 请向项目中添加一个。  
  
 该类是在动态链接库 (DLL) 或未在项目中直接引用的程序集中定义的。 Visual Basic 编译器需要引用以避免多义性的类定义在多个 DLL 或程序集。  
  
 **错误 ID:** BC30007  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 将未引用的 DLL 或程序集名称包括在项目引用中。  
  
## <a name="see-also"></a>请参阅

- [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)
- [有关无效的引用的疑难解答](/visualstudio/ide/troubleshooting-broken-references)
