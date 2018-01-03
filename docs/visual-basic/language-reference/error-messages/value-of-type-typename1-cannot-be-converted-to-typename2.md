---
title: "值的类型 &#39;&lt;typename1&gt;&#39; 不能转换为 &#39;&lt;typename2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords: BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b583c4272dd6e964de99fb14d2795152c655f3aa
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>值的类型 &#39;&lt;typename1&gt;&#39; 不能转换为 &#39;&lt;typename2&gt;&#39;
类型的值\<typename1 > 不能转换为\<typename2 >。 类型不匹配可能是由于文件引用与程序集的项目引用混合使用\<程序集名称 >。 请尝试替换为对的文件引用\<filepath > 项目中\<projectname1 > 的项目引用与\<项目名称 2> >。  
  
 在项目中进行项目引用和文件引用的情况下，编译器不能保证一个类型可转换为另一个。  
  
 下面的伪代码说明可以生成此错误的情况。  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 项目`P1`通过项目间接的项目引用`P2`到项目`P3`，同时还对直接文件引用`P3`。 声明`commonObject`使用对的文件引用`P3`，而对的调用`P2.getCommonClass`使用到的项目引用`P3`。  
  
 这种情况下的问题是文件引用指定的文件路径和名称的输出文件`P3`(通常为 p3.dll)，而项目引用标识源项目 (`P3`) 按项目名称。 因此，编译器也不能保证类型`P3.commonClass`来自通过两个不同引用相同的源代码。  
  
 这种情况通常发生在项目引用和混合文件引用。 上图中，问题可能不会发生如果`P1`所做的直接项目引用`P3`而不是文件引用。  
  
 **错误 ID:** BC30955  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   更改对项目引用的文件引用。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Basic 中的类型转换](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)  
 
