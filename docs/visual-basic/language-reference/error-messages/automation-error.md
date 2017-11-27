---
title: "自动错误"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 790b171b8d4022bd6d8b038c4221f24805ae42f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="automation-error"></a>自动错误
执行方法或者获取或设置对象变量的属性时发生错误。 错误由创建该对象的应用程序报告。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查 `Err` 对象的属性，以确定错误来源和错误性质。  
  
2.  在紧邻访问语句之前使用 `On Error Resume Next` 语句，然后检查紧邻访问语句之后是否存在错误。  
  
## <a name="see-also"></a>另请参阅  
 [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [与我们交流](/visualstudio/ide/talk-to-us)
