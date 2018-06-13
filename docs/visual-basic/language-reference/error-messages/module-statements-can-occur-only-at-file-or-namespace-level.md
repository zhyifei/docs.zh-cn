---
title: '&#39;模块&#39;语句只能出现在文件级或命名空间级'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 53199c2d7081445dc5490d5c54c98f93ee7522eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593160"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39;模块&#39;语句只能出现在文件级或命名空间级
`Module` 语句必须出现在源文件的顶部后立即`Option`和`Imports`语句、 全局属性和命名空间声明，但所有其他声明之前。  
  
 **错误 ID:** BC30617  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   移动`Module`到你的命名空间声明或源文件文件顶部的语句。  
  
## <a name="see-also"></a>请参阅  
 [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)
