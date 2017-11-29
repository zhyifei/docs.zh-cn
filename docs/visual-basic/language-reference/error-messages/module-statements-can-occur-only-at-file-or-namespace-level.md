---
title: "&#39;模块 &#39;语句只能出现在文件级或命名空间级"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords: BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61fe12fbd7d20e6cd2b6bc464e7fc3293150213b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39;模块 &#39;语句只能出现在文件级或命名空间级
`Module`语句必须出现在源文件的顶部后立即`Option`和`Imports`语句、 全局属性和命名空间声明，但所有其他声明之前。  
  
 **错误 ID:** BC30617  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   移动`Module`到你的命名空间声明或源文件文件顶部的语句。  
  
## <a name="see-also"></a>另请参阅  
 [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)
