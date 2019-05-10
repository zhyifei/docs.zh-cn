---
title: 在“<name>”中找不到任何具有合适签名的可访问“Main”方法
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 559c905d1e2e2de4500771a93d6116f9630011ba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591974"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>任何具有合适签名的可访问 Main 方法中找到\<名称 >
命令行应用程序必须具有`Sub Main`定义。 `Main` 必须声明为`Public Shared`如果它定义在类中，或作为`Public`如果模块中定义。  
  
 **错误 ID:** BC30737  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 定义`Public Sub Main`为你的项目的过程。 将其声明为`Shared`当且仅当在类定义。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 程序的结构](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
