---
title: 没有可访问&#39;Main&#39;中找到具有合适签名的方法&#39;&lt;名称&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 3398195ef9d503e47ab569ff85cb2a827c4270f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501485"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>没有可访问&#39;Main&#39;中找到具有合适签名的方法&#39;&lt;名称&gt;&#39;
命令行应用程序必须具有`Sub Main`定义。 `Main` 必须声明为`Public Shared`如果它定义在类中，或作为`Public`如果模块中定义。  
  
 **错误 ID:** BC30737  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   定义`Public Sub Main`为你的项目的过程。 将其声明为`Shared`当且仅当在类定义。  
  
## <a name="see-also"></a>请参阅
- [Visual Basic 程序的结构](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
