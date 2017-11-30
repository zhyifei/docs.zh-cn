---
title: "#<a name=\"externalsource-directive\"></a>ExternalSource 指令"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
caps.latest.revision: "160"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f90b838e50b65b8652cd9cf6f6ee084e9552f025
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="externalsource-directive"></a>#ExternalSource 指令
指示代码的源代码的特定行和源的外部文本之间的映射。  
  
## <a name="syntax"></a>语法  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>部件  
 `StringLiteral`  
 外部源的路径。  
  
 `IntLiteral`  
 外部源的第一行的行号。  
  
 `LogicalLine`  
 外部源中出现错误的行。  
  
 `#End ExternalSource`  
 终止 `#ExternalSource` 块。  
  
## <a name="remarks"></a>备注  
 使用此指令时仅由编译器和调试器。  
  
 源文件可能包含外部源指令，指示特定的源文件中的代码行和源，例如一个.aspx 文件的外部文本之间的映射。 如果在编译期间指定的源代码中遇到错误，则将它们标识作为来自外部源中。  
  
 外部源指令不会影响编译，而且不能嵌套。 它们是由应用程序仅供内部使用。  
  
## <a name="see-also"></a>另请参阅  
 [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
